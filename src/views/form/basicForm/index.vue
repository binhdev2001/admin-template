<template>
  <div>
    <div class="n-layout-page-header">
      <n-card :bordered="false" title="Biểu Mẫu Cơ Bản">
        Trang biểu mẫu được sử dụng để thu thập hoặc xác minh thông tin từ người dùng, biểu mẫu cơ bản thường xuất hiện trong các tình huống biểu mẫu có ít mục dữ liệu. Nhãn biểu mẫu cũng có thể hỗ trợ đáp ứng.
      </n-card>
    </div>
    <n-card :bordered="false" class="mt-4 proCard">
      <n-grid cols="1 s:1 m:3 l:3 xl:3 2xl:3" responsive="screen">
        <n-grid-item offset="0 s:0 m:1 l:1 xl:1 2xl:1">
          <n-form
            :label-width="90"
            :model="formValue"
            :rules="rules"
            label-placement="left"
            ref="formRef"
            class="py-8"
          >
            <n-form-item label="Tên Đặt Hẹn" path="name">
              <n-input v-model:value="formValue.name" placeholder="Nhập tên" />
            </n-form-item>
            <n-form-item label="Số Điện Thoại" path="mobile">
              <n-input placeholder="Số điện thoại" v-model:value="formValue.mobile" />
            </n-form-item>
            <n-form-item label="Thời Gian Đặt Hẹn" path="datetime">
              <n-date-picker type="datetime" v-model:value="formValue.datetime" />
            </n-form-item>
            <n-form-item label="Bác Sĩ Đặt Hẹn" path="doctor">
              <n-select
                placeholder="Chọn bác sĩ đặt hẹn"
                :options="doctorList"
                v-model:value="formValue.doctor"
              />
            </n-form-item>
            <n-form-item label="Nội Dung Đặt Hẹn" path="matter">
              <n-select
                placeholder="Chọn nội dung đặt hẹn"
                :options="matterList"
                v-model:value="formValue.matter"
                multiple
              />
            </n-form-item>
            <n-form-item label="Giới Tính" path="sex">
              <n-radio-group v-model:value="formValue.sex" name="sex">
                <n-space>
                  <n-radio :value="1">Nam</n-radio>
                  <n-radio :value="2">Nữ</n-radio>
                </n-space>
              </n-radio-group>
            </n-form-item>
            <n-form-item label="Ghi Chú Đặt Hẹn" path="remark">
              <n-input
                v-model:value="formValue.remark"
                type="textarea"
                placeholder="Nhập ghi chú đặt hẹn"
              />
            </n-form-item>
            <n-form-item label="Hình Ảnh" path="img">
              <BasicUpload
                :action="`${uploadUrl}/v1.0/files`"
                :headers="uploadHeaders"
                :data="{ type: 0 }"
                name="files"
                :width="100"
                :height="100"
                @upload-change="uploadChange"
                v-model:value="uploadList"
                helpText="Mỗi tệp không quá 20MB, tối đa chỉ có thể tải lên 10 tệp"
              />
            </n-form-item>
            <div style="margin-left: 80px">
              <n-space>
                <n-button type="primary" @click="formSubmit">Gửi Đặt Hẹn</n-button>
                <n-button @click="resetForm">Đặt Lại</n-button>
              </n-space>
            </div>
          </n-form>
        </n-grid-item>
      </n-grid>
    </n-card>
  </div>
</template>

<script lang="ts" setup>
  import { ref, unref, reactive } from 'vue';
  import { useMessage } from 'naive-ui';
  import { BasicUpload } from '@/components/Upload';
  import { useGlobSetting } from '@/hooks/setting';

  const globSetting = useGlobSetting();

  const matterList = [
    {
      label: 'Trồng Răng',
      value: 1,
    },
    {
      label: 'Trám Răng',
      value: 2,
    },
    {
      label: 'Điều Trị Tủy',
      value: 3,
    },
  ];

  const doctorList = [
    {
      label: 'Bác Sĩ Lý',
      value: 1,
    },
    {
      label: 'Bác Sĩ Hoàng',
      value: 2,
    },
    {
      label: 'Bác Sĩ Trương',
      value: 3,
    },
  ];

  const rules = {
    name: {
      required: true,
      message: 'Vui lòng nhập tên đặt hẹn',
      trigger: 'blur',
    },
    remark: {
      required: true,
      message: 'Vui lòng nhập ghi chú đặt hẹn',
      trigger: 'blur',
    },
    mobile: {
      required: true,
      message: 'Vui lòng nhập số điện thoại',
      trigger: ['input'],
    },
    datetime: {
      required: true,
      type: 'number',
      message: 'Vui lòng chọn thời gian đặt hẹn',
      trigger: ['blur', 'change'],
    },
    doctor: {
      required: true,
      type: 'number',
      message: 'Vui lòng chọn bác sĩ đặt hẹn',
      trigger: 'change',
    },
  };

  const formRef: any = ref(null);
  const message = useMessage();
  const { uploadUrl } = globSetting;

  const defaultValueRef = () => ({
    name: '',
    mobile: '',
    remark: '',
    sex: 1,
    matter: null,
    doctor: null,
    datetime: [],
  });

  let formValue = reactive(defaultValueRef());
  const uploadList = ref([
    'https://zos.alipayobjects.com/rmsportal/jkjgkEfvpUPVyRjUImniVslZfWPnJuuZ.png',
  ]);
  const uploadHeaders = reactive({
    platform: 'miniPrograms',
    timestamp: new Date().getTime(),
    token: 'Q6fFCuhc1vkKn5JNFWaCLf6gRAc5n0LQHd08dSnG4qo=',
  });

  function formSubmit() {
    formRef.value.validate((errors) => {
      if (!errors) {
        message.success('Xác minh thành công');
      } else {
        message.error('Xác minh thất bại, vui lòng điền đầy đủ thông tin');
      }
    });
  }

  function resetForm() {
    formRef.value.restoreValidation();
    formValue = Object.assign(unref(formValue), defaultValueRef());
  }

  function uploadChange(list: string[]) {
    console.log(list);
  }
</script>

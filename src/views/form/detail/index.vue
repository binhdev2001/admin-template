<template>
  <div>
    <div class="n-layout-page-header">
      <n-card :bordered="false" title="Chi tiết biểu mẫu">
        Biểu mẫu ngoài việc gửi dữ liệu, đôi khi cũng được sử dụng để hiển thị thông tin chỉ đọc.
      </n-card>
    </div>
    <n-card
      :bordered="false"
      title="Thông tin cơ bản"
      class="mt-4 proCard"
      size="small"
      :segmented="{ content: true }"
    >
      <n-descriptions label-placement="left" class="py-2">
        <n-descriptions-item>
          <template #label>Tên người nhận</template>
          Ah jung
        </n-descriptions-item>
        <n-descriptions-item label="Tài khoản nhận">NaiveUiAdmin@qq.com</n-descriptions-item>
        <n-descriptions-item label="Loại thanh toán">Alipay</n-descriptions-item>
        <n-descriptions-item label="Tài khoản thanh toán">NaiveUiAdmin@163.com</n-descriptions-item>
        <n-descriptions-item label="Số tiền chuyển">￥1980.00</n-descriptions-item>
        <n-descriptions-item label="Trạng thái">
          <n-tag type="success"> Đã nhận</n-tag>
        </n-descriptions-item>
      </n-descriptions>
    </n-card>
    <n-card
      :bordered="false"
      title="Thông tin khác"
      class="mt-4 proCard"
      size="small"
      :segmented="{ content: true }"
    >
      <n-descriptions label-placement="left" class="py-2">
        <n-descriptions-item>
          <template #label>Thành phố</template>
          Thâm Quyến
        </n-descriptions-item>
        <n-descriptions-item label="Giới tính">Nam</n-descriptions-item>
        <n-descriptions-item label="Email">NaiveUiAdmin@qq.com</n-descriptions-item>
        <n-descriptions-item label="Địa chỉ">Quận Nam Sơn, Thâm Quyến, tỉnh Quảng Đông</n-descriptions-item>
        <n-descriptions-item label="Ngày sinh">1991-06-04</n-descriptions-item>
        <n-descriptions-item label="Xác thực">
          <n-tag type="success"> Đã xác thực</n-tag>
        </n-descriptions-item>
      </n-descriptions>
    </n-card>
    <n-card
      :bordered="false"
      title="Thông tin bảng"
      class="mt-4 proCard"
      size="small"
      :segmented="{ content: true }"
    >
      <n-table :bordered="false" :single-line="false">
        <thead>
          <tr>
            <th>Tên</th>
            <th>Giới tính</th>
            <th>Thành phố</th>
            <th>Ngày sinh</th>
            <th width="150">Hành động</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Ah jung</td>
            <td>Nam</td>
            <td>Thâm Quyến</td>
            <td>1993-11-09</td>
            <td>
              <n-space>
                <n-button size="small" type="error">Xóa</n-button>
                <n-button size="small" type="info">Xem</n-button>
              </n-space>
            </td>
          </tr>
          <tr>
            <td>Tây Môn Phi Tuyết</td>
            <td>Nam</td>
            <td>Quảng Châu</td>
            <td>1991-09-11</td>
            <td>
              <n-space>
                <n-button size="small" type="error">Xóa</n-button>
                <n-button size="small" type="info">Xem</n-button>
              </n-space>
            </td>
          </tr>
          <tr>
            <td>Người khổng lồ Titan</td>
            <td>Nam</td>
            <td>Bắc Kinh</td>
            <td>1990-11-03</td>
            <td>
              <n-space>
                <n-button size="small" type="error">Xóa</n-button>
                <n-button size="small" type="info">Xem</n-button>
              </n-space>
            </td>
          </tr>
          <tr>
            <td>Thợ săn quái vật</td>
            <td>Nữ</td>
            <td>Thượng Hải</td>
            <td>1992-03-11</td>
            <td>
              <n-space>
                <n-button size="small" type="error">Xóa</n-button>
                <n-button size="small" type="info">Xem</n-button>
              </n-space>
            </td>
          </tr>
        </tbody>
      </n-table>
    </n-card>
  </div>
</template>

<script setup></script>

<style lang="less" scoped></style>

<template>
  <div>
    <div class="n-layout-page-header">
      <n-card :bordered="false" title="Bàn làm việc">
        <n-grid cols="2 s:1 m:1 l:2 xl:2 2xl:2" responsive="screen">
          <n-gi>
            <div class="flex items-center">
              <div>
                <n-avatar circle :size="64" :src="schoolboy" />
              </div>
              <div>
                <p class="px-4 text-xl">Chào buổi sáng, Ah jung, bắt đầu một ngày làm việc của bạn nhé!</p>
                <p class="px-4 text-gray-400">Hôm nay trời âm u chuyển mưa lớn, 15℃ - 25℃, nhớ mang ô khi ra ngoài nhé.</p>
              </div>
            </div>
          </n-gi>
          <n-gi>
            <div class="flex justify-end w-full">
              <div class="flex flex-col justify-center flex-1 text-right">
                <span class="text-secondary">Số dự án</span>
                <span class="text-2xl">16</span>
              </div>
              <div class="flex flex-col justify-center flex-1 text-right">
                <span class="text-secondary">Việc cần làm</span>
                <span class="text-2xl">3/15</span>
              </div>
              <div class="flex flex-col justify-center flex-1 text-right">
                <span class="text-secondary">Tin nhắn</span>
                <span class="text-2xl">35</span>
              </div>
            </div>
          </n-gi>
        </n-grid>
      </n-card>
    </div>
    <n-grid class="mt-4" cols="2 s:1 m:1 l:2 xl:2 2xl:2" responsive="screen" :x-gap="12" :y-gap="9">
      <n-gi>
        <n-card
          :segmented="{ content: true }"
          content-style="padding: 0;"
          :bordered="false"
          size="small"
          title="Dự án"
        >
          <div class="flex flex-wrap project-card">
            <n-card
              size="small"
              class="cursor-pointer project-card-item ms:w-1/2 md:w-1/3"
              hoverable
            >
              <div class="flex">
                <span>
                  <n-icon size="30">
                    <GithubOutlined />
                  </n-icon>
                </span>
                <span class="ml-4 text-lg">Github</span>
              </div>
              <div class="flex h-10 mt-2 text-gray-400">
                Là một nền tảng lưu trữ dự án phần mềm mã nguồn mở và riêng tư.
              </div>
              <div class="flex h-10 mt-2 text-gray-400"> Mở nguồn君，2021-07-04 </div>
            </n-card>
            <n-card
              size="small"
              class="cursor-pointer project-card-item ms:w-1/2 md:w-1/3"
              hoverable
            >
              <div class="flex">
                <span>
                  <n-icon size="30" color="#42b983">
                    <LogoVue />
                  </n-icon>
                </span>
                <span class="ml-4 text-lg">Vue</span>
              </div>
              <div class="flex h-10 mt-2 text-gray-400"> Khung JavaScript tiến bộ </div>
              <div class="flex h-10 mt-2 text-gray-400"> Học không nổi cũng phải học, 2021-07-04 </div>
            </n-card>
            <n-card
              size="small"
              class="cursor-pointer project-card-item ms:w-1/2 md:w-1/3"
              hoverable
            >
              <div class="flex">
                <span>
                  <n-icon size="30" color="#e44c27">
                    <Html5Outlined />
                  </n-icon>
                </span>
                <span class="ml-4 text-lg">Html5</span>
              </div>
              <div class="flex h-10 mt-2 text-gray-400"> HTML5 là tiêu chuẩn tiếp theo của Internet. </div>
              <div class="flex h-10 mt-2 text-gray-400"> Viết mã cũng là một nghệ thuật 2021-04-01 </div>
            </n-card>
            <n-card
              size="small"
              class="cursor-pointer project-card-item ms:w-1/2 md:w-1/3"
              hoverable
            >
              <div class="flex">
                <span>
                  <n-icon size="30" color="#dd0031">
                    <LogoAngular />
                  </n-icon>
                </span>
                <span class="ml-4 text-lg">Angular</span>
              </div>
              <div class="flex h-10 mt-2 text-gray-400"> Nền tảng phát triển Web hiện đại, được hàng triệu người hâm mộ. </div>
              <div class="flex h-10 mt-2 text-gray-400"> Fan cứng 2021-07-04。 </div>
            </n-card>
            <n-card
              size="small"
              class="cursor-pointer project-card-item ms:w-1/2 md:w-1/3"
              hoverable
            >
              <div class="flex">
                <span>
                  <n-icon size="30" color="#61dafb">
                    <LogoReact />
                  </n-icon>
                </span>
                <span class="ml-4 text-lg">React</span>
              </div>
              <div class="flex h-10 mt-2 text-gray-400"> Thư viện JavaScript để xây dựng giao diện người dùng. </div>
              <div class="flex h-10 mt-2 text-gray-400"> Kỹ thuật viên 2021-07-04。 </div>
            </n-card>
            <n-card
              size="small"
              class="cursor-pointer project-card-item ms:w-1/2 md:w-1/3"
              hoverable
            >
              <div class="flex">
                <span>
                  <n-icon size="30">
                    <LogoJavascript />
                  </n-icon>
                </span>
                <span class="ml-4 text-lg">Js</span>
              </div>
              <div class="flex h-10 mt-2 text-gray-400"> Đường là đi ra chứ không phải tưởng tượng ra. </div>
              <div class="flex h-10 mt-2 text-gray-400"> Nhóm kiến trúc 2021-07-04 </div>
            </n-card>
          </div>
        </n-card>

        <n-card
          :segmented="{ content: true }"
          content-style="padding-top: 0;padding-bottom: 0;"
          :bordered="false"
          size="small"
          title="Hoạt động"
          class="mt-4"
        >
          <template #header-extra><a href="javascript:;">Xem thêm</a></template>
          <n-list>
            <n-list-item>
              <template #prefix>
                <n-avatar circle :size="40" :src="schoolboy" />
              </template>
              <n-thing title="Ah Jung vừa viết một số thứ trên trang bàn làm việc, tạm thời có thể xem được!">
                <template #description
                  ><p class="text-xs text-gray-500">2021-07-04 22:37:16</p></template
                >
              </n-thing>
            </n-list-item>
            <n-list-item>
              <template #prefix>
                <n-avatar circle :size="40" :src="schoolboy" />
              </template>
              <n-thing title="Ah Jung đã tạo dự án naive-ui-admin trong nhóm Mở nguồn?">
                <template #description
                  ><p class="text-xs text-gray-500">2021-07-04 09:37:16</p></template
                >
              </n-thing>
            </n-list-item>
            <n-list-item>
              <template #prefix>
                <n-avatar circle :size="40" :src="schoolboy" />
              </template>
              <n-thing title="@It界风清扬, đã gửi một lỗi cho naive-ui-admin, hãy xem khi có thời gian!">
                <template #description
                  ><p class="text-xs text-gray-500">2021-07-04 22:37:16</p></template
                >
              </n-thing>
            </n-list-item>
            <n-list-item>
              <template #prefix>
                <n-avatar circle :size="40" :src="schoolboy" />
              </template>
              <n-thing title="Các bạn trong phòng kỹ thuật, cảnh báo lần nữa, đừng lười biếng, đừng lười biếng, đừng lười biếng nữa!">
                <template #description
                  ><p class="text-xs text-gray-500">2021-07-04 09:37:16</p></template
                >
              </n-thing>
            </n-list-item>
            <n-list-item>
              <template #prefix>
                <n-avatar circle :size="40" :src="schoolboy" />
              </template>
              <n-thing title="Đi làm mà không lười biếng, thì khác gì cá khô (câu này không phải tôi nói đâu nhé)!">
                <template #description
                  ><p class="text-xs text-gray-500">2021-07-04 20:37:16</p></template
                >
              </n-thing>
            </n-list-item>
            <n-list-item>
              <template #prefix>
                <n-avatar circle :size="40" :src="schoolboy" />
              </template>
              <n-thing title="Chuyển trang thực ra cũng hỗ trợ bộ nhớ đệm, chỉ là thêm hiệu ứng chuyển đổi, nhìn như là render lại">
                <template #description>
                  <p class="text-gray-400">
                    <n-input type="text" placeholder="Không tin, thử nhập một số văn bản" />
                  </p>
                </template>
              </n-thing>
            </n-list-item>
          </n-list>
        </n-card>
      </n-gi>
      <n-gi>
        <n-card
          :segmented="{ content: true }"
          content-style="padding: 0;"
          :bordered="false"
          size="small"
          title="Tác vụ nhanh"
        >
          <div class="flex flex-wrap project-card">
            <n-card size="small" class="cursor-pointer project-card-item" hoverable>
              <div class="flex flex-col justify-center text-gray-500">
                <span class="text-center">
                  <n-icon size="30" color="#68c755">
                    <DashboardOutlined />
                  </n-icon>
                </span>
                <span class="text-center text-lx">Bảng điều khiển</span>
              </div>
            </n-card>
            <n-card size="small" class="cursor-pointer project-card-item" hoverable>
              <div class="flex flex-col justify-center text-gray-500">
                <span class="text-center">
                  <n-icon size="30" color="#fab251">
                    <ProfileOutlined />
                  </n-icon>
                </span>
                <span class="text-center text-lx">Danh sách</span>
              </div>
            </n-card>
            <n-card size="small" class="cursor-pointer project-card-item" hoverable>
              <div class="flex flex-col justify-center text-gray-500">
                <span class="text-center">
                  <n-icon size="30" color="#1890ff">
                    <FileProtectOutlined />
                  </n-icon>
                </span>
                <span class="text-center text-lx">Biểu mẫu</span>
              </div>
            </n-card>
            <n-card size="small" class="cursor-pointer project-card-item" hoverable>
              <div class="flex flex-col justify-center text-gray-500">
                <span class="text-center">
                  <n-icon size="30" color="#f06b96">
                    <ApartmentOutlined />
                  </n-icon>
                </span>
                <span class="text-center text-lx">Quản lý quyền</span>
              </div>
            </n-card>
            <n-card size="small" class="cursor-pointer project-card-item" hoverable>
              <div class="flex flex-col justify-center text-gray-500">
                <span class="text-center">
                  <n-icon size="30" color="#7238d1">
                    <SettingOutlined />
                  </n-icon>
                </span>
                <span class="text-center text-lx">Quản lý hệ thống</span>
              </div>
            </n-card>
            <n-card size="small" class="cursor-pointer project-card-item" hoverable>
              <div class="flex flex-col justify-center text-gray-500">
                <span class="text-center">
                  <n-icon size="30" color="">
                    <DashboardOutlined />
                  </n-icon>
                </span>
                <span class="text-center text-lx">Bảng điều khiển</span>
              </div>
            </n-card>
          </div>
        </n-card>
        <n-card :segmented="{ content: true }" :bordered="false" size="small" class="mt-4">
          <img src="~@/assets/images/Business.svg" class="w-full" />
        </n-card>
      </n-gi>
    </n-grid>
  </div>
</template>

<script lang="ts">
  export default { name: 'DashboardWorkplace' };
</script>

<script lang="ts" setup>
  import schoolboy from '@/assets/images/schoolboy.png';
  import {
    GithubOutlined,
    DashboardOutlined,
    ProfileOutlined,
    FileProtectOutlined,
    SettingOutlined,
    ApartmentOutlined,
    Html5Outlined,
  } from '@vicons/antd';
  import { LogoVue, LogoAngular, LogoReact, LogoJavascript } from '@vicons/ionicons5';
</script>

<style lang="less" scoped>
  .project-card {
    margin-right: -6px;

    &-item {
      margin: -1px;
      width: 33.333333%;
    }
  }
</style>

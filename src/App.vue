<template>
  <div id="app">
    <v-runtime-template :template="template"></v-runtime-template>
  </div>
</template>

<script>
import VRuntimeTemplate from "v-runtime-template";
import AppMessage from "./AppMessage";

export default {
  data: () => ({
    missionList: [
      {
        missionId: 282,
        title:
          "\u4efb\u52a11\uff1a\u5b9a\u91cf\u57ce\u5e02\u7814\u7a76\u4e3a\u4ec0\u4e48\u9700\u8981Python\uff1f\uff08\u514d\u8d39\u8bd5\u5b66\uff09",
        sortNum: 1,
      },
      {
        missionId: 293,
        title: "\u4efb\u52a12\uff1a\u5feb\u901f\u638c\u63e1Python\u57fa\u7840",
        sortNum: 2,
      },
      {
        missionId: 294,
        title:
          "\u4efb\u52a13\uff1a\u8ba4\u8bc6\u591a\u7ef4\u6570\u7ec4\u2014\u2014Numpy",
        sortNum: 3,
      },
      {
        missionId: 295,
        title:
          "\u4efb\u52a14\uff1a\u5904\u7406\u8868\u683c\u6570\u636e\u2014\u2014Pandas",
        sortNum: 4,
      },
      {
        missionId: 296,
        title:
          "\u4efb\u52a15\uff1a\u7ed8\u5236\u57fa\u7840\u56fe\u5f62\u2014\u2014Matplotlib",
        sortNum: 5,
      },
      {
        missionId: 299,
        title:
          "\u4efb\u52a16\uff1a\u7ed8\u5236\u7edf\u8ba1\u56fe\u5f62\u2014\u2014Seaborn",
        sortNum: 6,
      },
      {
        missionId: 300,
        title:
          "\u4efb\u52a17\uff1a\u5904\u7406\u7a7a\u95f4\u6570\u636e\u2014\u2014Shapely\u4e0eGeopandas",
        sortNum: 7,
      },
      {
        missionId: 302,
        title:
          "\u4efb\u52a18\uff1a\u8fdb\u884c\u7f51\u7edc\u5206\u6790\u2014\u2014Networkx",
        sortNum: 8,
      },
      {
        missionId: 291,
        title:
          "\u4efb\u52a19\uff1a\u521d\u9636\u5b9e\u6218\u2014\u2014\u57fa\u4e8e\u9ad8\u94c1\u4f59\u7968\u7684\u5ba2\u6d41\u884c\u4e3a\u7279\u5f81\u53ca\u5176\u6548\u5e94\u5206\u6790\u3010\u57ce\u5e02\u89c4\u5212\u3011",
        sortNum: 9,
      },
      {
        missionId: 292,
        title:
          "\u4efb\u52a110\uff1a\u521d\u9636\u5b9e\u6218\u2014\u2014\u57fa\u4e8e\u591a\u6e90\u6570\u636e\u65f6\u7a7a\u71b5\u7684\u57ce\u5e02\u529f\u80fd\u6df7\u5408\u5ea6\u8bc6\u522b\u8bc4\u4ef7\u3010\u57ce\u5e02\u89c4\u5212\u3011",
        sortNum: 10,
      },
      {
        missionId: 307,
        title:
          "\u4efb\u52a111\uff1a\u521d\u9636\u5b9e\u6218\u2014\u2014\u516c\u5171\u4ea4\u901a\u5f71\u54cd\u4e0b\u7684\u5317\u4eac\u516c\u5171\u670d\u52a1\u8bbe\u65bd\u53ef\u8fbe\u6027\u3010\u5730\u7406\u79d1\u5b66\u8fdb\u5c55 \u3011",
        sortNum: 11,
      },
      {
        missionId: 303,
        title:
          "\u4efb\u52a112\uff1a\u4e2d\u9636\u5b9e\u6218\u2014\u2014\u4e0a\u6d77\u8f68\u9053\u4ea4\u901a\u4e0e\u4eba\u53e3\u548c\u5c31\u4e1a\u5c97\u4f4d\u5e03\u5c40\u7684\u8026\u5408\u5206\u6790\u3010\u57ce\u5e02\u89c4\u5212\u5b66\u520a\u3011",
        sortNum: 12,
      },
      {
        missionId: 304,
        title:
          "\u4efb\u52a113\uff1a\u4e2d\u9636\u5b9e\u6218\u2014\u2014\u4e2d\u56fd\u57ce\u5e02\u95f4\u4eba\u53e3\u6d41\u52a8\u7a7a\u95f4\u683c\u5c40\u7684\u7f51\u7edc\u5206\u6790\u3010\u5730\u7406\u7814\u7a76\u3011",
        sortNum: 13,
      },
      {
        missionId: 306,
        title:
          "\u4efb\u52a114\uff1a\u9ad8\u9636\u5b9e\u6218\u2014\u2014An empirical analysis of dockless bike-sharing utilization\u3010Journal of Transport Geography\u3011",
        sortNum: 14,
      },
      {
        missionId: 305,
        title:
          "\u4efb\u52a115\uff1a\u9ad8\u9636\u5b9e\u6218\u2014\u2014Mapping the spatio-temporal distribution of solar radiation within street canyons\u3010Landscape and Urban Planning\u3011",
        sortNum: 15,
      },
      {
        missionId: 309,
        title:
          "\u4efb\u52a116\uff1a\u79d1\u7814\u52a9\u529b\u2014\u2014\u6570\u636e\u52a9\u529b\u5b66\u672f\u6210\u679c",
        sortNum: 16,
      },
    ],
    name: "Mellow",
    template: `
      <div class="introduce-content">
    <div class="ic-header">
      <picture class="picture">
        <source
          type="image/webp"
          srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/1.webp"
        />
        <img
          class="image"
          src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/1.jpg"
          alt=""
        >
      </picture>
    </div>
    <div class="ic-content ic-100">
      <picture class="picture">
        <source
          type="image/webp"
          srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/2.webp"
        />
        <img
          class="image"
          src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/2.jpg"
          alt=""
        >
      </picture>

      <!--                课程特色-->
      <div class="ic-features">
        <picture class="picture">
          <source
            type="image/webp"
            srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/3.webp"
          />
          <img
            class="image"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/3.jpg"
            alt=""
          >
        </picture>
        <div class="abArea">
          <div class="cardT1 flex jc">
            <div class="flex ac jc dc python_new">
              <div class="imgArea">
                <picture class="picture">
                  <source
                    type="image/webp"
                    srcset="https://www.lifangshuju.com/static/imgs/ad3.webp"
                  />
                  <img
                    class="image"
                    src="https://www.lifangshuju.com/static/imgs/ad3.png"
                  />
                </picture>
              </div>
              <p class="t1 s">- 课程内容 -</p>
              <p class="t2">工匠式精心打磨</p>
              <ul class="desc s">
                <li>
                  <span>内容系统全面</span>
                </li>
                <li>
                  <span>注重实战场景</span>
                </li>
                <li>
                  <span>采用一线数据</span>
                </li>
              </ul>
            </div>
            <div class="flex ac jc dc python_new">
              <div class="imgArea">
                <picture class="picture">
                  <source
                    type="image/webp"
                    srcset="https://www.lifangshuju.com/static/imgs/ad2.webp"
                  />
                  <img
                    class="image"
                    src="https://www.lifangshuju.com/static/imgs/ad2.png"
                  />
                </picture>
              </div>
              <p class="t1">- 上课形式 -</p>
              <p class="t2">交互智能课堂</p>
              <ul class="desc">
                <li>
                  <span>对话式课程，学习就像跟老师<br />在微信聊天，不无聊</span>
                </li>
                <li>
                  <span>全网首家在线Notebook教学<br />环境，学习更轻松</span>
                </li>
              </ul>
            </div>
            <div class="flex ac jc dc python_new">
              <div class="imgArea">
                <picture class="picture">
                  <source
                    type="image/webp"
                    srcset="https://www.lifangshuju.com/static/imgs/ad1.webp"
                  />
                  <img
                    class="image"
                    src="https://www.lifangshuju.com/static/imgs/ad1.png"
                  />
                </picture>
              </div>
              <p class="t1 s">- 课程服务 -</p>
              <p class="t2">保姆式学习服务</p>
              <ul class="desc s">
                <li>
                  <span>微信群答疑</span>
                </li>
                <li>
                  <span>监督学习</span>
                </li>
                <li>
                  <span>作业批改</span>
                </li>
                <li>
                  <span>发放证书</span>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
      <div class="ic-100">
        <picture class="picture">
          <source
            type="image/webp"
            srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/4.webp"
          />
          <img
            class="image"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/4.jpg"
            alt=""
          >
        </picture>
      </div>
      <div class="ic-100">
        <picture class="picture">
          <source
            type="image/webp"
            srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/5.webp"
          />
          <img
            class="image"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/5.jpg"
            alt=""
          >
        </picture>
      </div>

      <!--                课程成果图-->
      <div class="ic-100">
        <picture class="picture">
          <source
            type="image/webp"
            srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/6.webp"
          />
          <img
            class="image"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/6.jpg"
            alt=""
          >
        </picture>
        <!--                课程大纲-->
        <div
          class="ic-point ic-100"
          style="background: rgb(242,248,253);"
        >
          <div class="ic-catalog">
            <div
              class="missionList python_new"
              style="padding-top: 0"
            >
              <div
                class="misItem"
                v-for="(mis, ind) in missionList"
                :key="ind"
              >
                <div class="flex ac js">
                  <div class="flex ac arrow-icon">
                    <span>{{ mis.title }}</span>
                    <span
                      v-show="mis.open && mis.rouList && mis.rouList.length > 0"
                      class="arrow-top"
                    ></span>
                  </div>
                  <div
                    class="btn pointer flex ac jc"
                    @click="openMis(mis)"
                  >
                    <i :class="[ mis.open ? 'el-icon-arrow-down' : 'el-icon-arrow-right']"></i>
                  </div>
                </div>
                <ul
                  class="rouList"
                  :style="{ maxHeight: mis.open ? (mis.rouList ? mis.rouList.length : 1) * 4.22 + 'rem' : 0}"
                >
                  <li
                    class="rouItem flex ac pointer"
                    v-for="(rou, rouInd) in mis.rouList"
                    :key="rouInd"
                  >
                    <!-- @click="goCourseDetail(rou)" -->
                    <div> 关卡{{ rouInd + 1 }} </div>
                    <div>{{ rou.title }}</div>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
        <picture class="picture">
          <source
            type="image/webp"
            srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/7.webp"
          />
          <img
            class="image"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/7.jpg"
            alt=""
          >
        </picture>

        <picture class="picture">
          <source
            type="image/webp"
            srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/9.webp"
          />
          <img
            class="image"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/9.jpg"
            alt=""
          >
        </picture>
        <picture class="picture">
          <source
            type="image/webp"
            srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/10.webp"
          />
          <img
            class="image"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/10.jpg"
            alt=""
          >
        </picture>
        <picture class="picture">
          <source
            type="image/webp"
            srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/11.webp"
          />
          <img
            class="image"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/11.jpg"
            alt=""
          >
        </picture>
        <div style="position: relative;">
          <picture class="picture">
            <source
              type="image/webp"
              srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/12_1.webp"
            />
            <img
              class="image"
              src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/12_1.jpg"
              alt=""
            >
          </picture>
          <img
            style="position:absolute;left:30rem;top:0rem;width:40rem;border-radius:.5rem;"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/12_2.png"
            alt=""
          >
          <img
            style="position:absolute;left:28.5rem;top:40.5rem;width:44rem;border-radius:.5rem;"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/12_3.png"
            alt=""
          >
          <img
            style="position:absolute;left:31.25rem;top:1rem;width:37.7rem;border-radius:.5rem;"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_base/pc/1.gif"
            alt=""
          >
          <img
            style="position:absolute;left:29.5rem;top:41.5rem;width:41.5rem;border-radius:.5rem;"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_base/pc/2.gif"
            alt=""
          >
        </div>
        <picture class="picture">
          <source
            type="image/webp"
            srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/13.webp"
          />
          <img
            class="image"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/13.jpg"
            alt=""
          >
        </picture>
        <picture class="picture">
          <source
            type="image/webp"
            srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/14.webp"
          />
          <img
            class="image"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/14.jpg"
            alt=""
          >
        </picture>
        <picture class="picture">
          <source
            type="image/webp"
            srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/15.webp"
          />
          <img
            class="image"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/15.jpg"
            alt=""
          >
        </picture>
        <div style="position: relative;">
          <picture class="picture">
            <source
              type="image/webp"
              srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/16.webp"
            />
            <img
              class="image"
              src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/16.jpg"
              alt=""
            >
          </picture>
          <div class="myswiperWrap" style="width:63rem;margin:0 auto; position:absolute;top:12.5rem;left:50%;margin-left:-31.5rem">
            <swiper ref="mySwiper" v-bind:options="swiperOptions">
              <swiper-slide>
                <img
                  style="width:54rem;height:22.7rem"
                  src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/pc1.jpg"
                >
              </swiper-slide>
              <swiper-slide>
                <img
                  style="width:54rem;height:22.7rem"
                  src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/pc2.jpg"
                >
              </swiper-slide>
              <swiper-slide>
                <img
                  style="width:54rem;height:22.7rem"
                  src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/pc3.jpg"
                >
              </swiper-slide>
              <div class="swiper-button-prev swiper-button-white" slot="button-prev"></div>
              <div class="swiper-button-next swiper-button-white" slot="button-next"></div>
            </swiper>
          </div>
        </div>
        <picture class="picture">
          <source
            type="image/webp"
            srcset="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/17.webp"
          />
          <img
            class="image"
            src="https://lifangdata.oss-cn-hangzhou.aliyuncs.com/introduce/python_new/pc/17.jpg"
            alt=""
          >
        </picture>
      </div>
    </div>
  </div>
    `,
  }),
  components: {
    AppMessage,
    VRuntimeTemplate,
  },
};
</script>

### SVG是什么？
SVG是一种可缩放矢量图形，是基于可扩展标记语言（XML），用于描述二维矢量图形的图形格式。

### 为什么我使用SVG？  
1. SVG在放大的过程中，不会失真
2. 可读性好，有利于SEO。由于SVG采用的是XML语法，图形里面的文本内容可以直接被浏览器搜索引擎SEO读屏软件读取。
3. 可以修改SVG颜色，不需要同一个样式的图标，准备不同的颜色。只需给SVG添加不同的class就可以修改SVG的颜色了。  

### 如何在项目中使用SVG？  
我们项目是vue项目  
第一步、封装了一个svg-icon组件，代码如下：  
 ``
    <template>
        <svg class='svg-icon' id="svgIcon" :class='iconClass' :viewBox='viewBox[iconClass]' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'>
            <g v-if="iconClass == 'icon-search'">
            <path d="M5.66666667,10.8333333 C2.81319546,10.8333333 0.5,8.52013787 0.5,5.66666667 C0.5,2.81319546 2.81319546,0.5 5.66666667,0.5 C8.52013787,0.5 10.8333333,2.81319546 10.8333333,5.66666667 C10.8333333,8.52013787 8.52013787,10.8333333 5.66666667,10.8333333 Z M5.66666667,9.83333333 C7.96785312,9.83333333 9.83333333,7.96785312 9.83333333,5.66666667 C9.83333333,3.36548021 7.96785312,1.5 5.66666667,1.5 C3.36548021,1.5 1.5,3.36548021 1.5,5.66666667 C1.5,7.96785312 3.36548021,9.83333333 5.66666667,9.83333333 Z"></path>
            <path d="M8.24644661,9.75355339 L11.4464466,12.9535534 C11.6417088,13.1488155 11.9582912,13.1488155 12.1535534,12.9535534 C12.3488155,12.7582912 12.3488155,12.4417088 12.1535534,12.2464466 L8.95355339,9.04644661 C8.75829124,8.85118446 8.44170876,8.85118446 8.24644661,9.04644661 C8.05118446,9.24170876 8.05118446,9.55829124 8.24644661,9.75355339 Z"></path>
        </g>
        </svg>
    </template>
    <script>
      export default {
          name: 'svg-icon',
          props: {
              iconClass: {
                  type: String
              }
          },
          data () {
              viewBox: {
                'icon-search': '0 0 14 14'  
              }
          }
      }
    </script>
    <style>
      .svg {line-height:1;display:inline-flex;align-items:center;}
      svg {fill: currentColor;max-height:64px;}
      .svg-icon {width:20px;height:20px;}
    </style>
``
第二步在组件中svg-icon  
``
<script>
   // 在组件中引入svg-icon组件
   import svgIcon from '@/components/svg-icon'
   
    // 在components注入svg-icon

    componets: {svgIcon}
</script>
  

// 在html中使用svg-icon
<svg-icon iconClass="icon-search"></svg-icon>
``

这样我们就在项目中使用SVG矢量图标了。
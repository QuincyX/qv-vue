import组件
```
import qv3dpost from '.././components/qv-3dpost.vue'
```
声明组件
```
export default {
  components: {
    qv3dpost
  }
}
```
使用组件
```
<qv-3dpost 
  width='100%' height="600px"
  backgroundimg="https://images.apple.com/cn/iphone/home/images/business_large.jpg"
>
  <p slot="v1" style="top:20px;left:600px;">第一层</p>
  <p slot="v2" style="top:200px;left:600px;">第二层</p>
  <p slot="v3" style="top:200px;left:60px;">第三层</p>
</qv-3dpost>
```
组件的css：width、height background-image已暴露出来   
三个slot为不同层次的层，定位使用absolute,只需添上top、left、bottom、right定位即可

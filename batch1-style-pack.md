# 第一批风格补充包：风格锚点 + 反例 + 按类型模板（试点先做白雾和裂纹）

先看锚点和反例，再画图。原著图在 batch1-source-png/，风格锚点在 batch1-style/style-anchor/，失败反例在 batch1-style/style-negative/，全部在公开仓库 main 分支上。

## 风格锚点（模组里现有的贴图，这才是要对齐的风格）
- style-anchor/gura_crack.png：模组现有的震裂，64x384 竖条，6 帧从小到大生长，裂纹分叉不规则、粗细不一，不是单张完美星芒。裂纹要按这个思路画：生长、分叉、不规则。
- style-anchor/hie_ice_wave.png：模组现有的冰浪，128x128，一整块扁平冰面加白色条纹，不是居中的冰晶图标。冰要按这个思路画：面积、条纹、不规则边缘。
- style-anchor/mat_ice.png、mat_smoke.png：模组现有的材质块，256x256，冰和烟都是一整块带噪点的面积，透明度、颜色深浅有变化，不是闭合形状、不是图标。雾和冰面要按这个思路画：面积、噪点、深浅变化。

## 反例（这 11 张就是错的，不要再画成这样）
- style-negative/hie_frost_mist.png：白色旋涡云图标，错在闭合形状、对称、光滑。
- style-negative/gura_air_crack.png：完美放射细星芒，错在居中、对称、等长、太细。
- style-negative/gura_shock_wave.png：干净断圆环，错在完美圆环、太干净。
- style-negative/hie_frozen_ground.png：斜向冰片重复铺满，错在墙纸式重复。
- style-negative/mera_flame_tongue.png：扁平火带，错在不卷曲、截断。
- style-negative/mera_ember.png：爪痕斜线，错在不是飘着的火点。
- style-negative/mera_scorch_ground.png：小黑盘加红蚯蚓线，错在太小、太规整。
- style-negative/goro_lightning_arc.png：蓝色火团，错在不是分叉电弧线。
- style-negative/goro_thunder_scorch.png：深紫黑墨点加蜘蛛丝，错在不是雷劈焦土。
- style-negative/hie_ice_shard.png：薄纸片，错在没有切面和厚度。
- style-negative/gura_ground_shatter.png：灰色烟团，错在不是土块加尘雾。

## 按类型模板（不要把所有贴图都画成居中物体）
- 物体类（火核、主闪、冰晶，已留用的 3 张就是这个类）：可以居中，但要有切面、黑边、粗细变化。
- 气氛类（白雾、裂纹、冲击波）：不能是闭合形状、不能居中对称、不能是完整物体。要铺满整张、破开、边缘毛糙、透明度深浅不一，裂纹要从偏离中心的位置起、分叉不规则、粗细不一。
- 地面类（焦土、冻面、碎裂、雷焦土）：不能是一个小圆盘、不能重复铺满。要是一块不规则地面，带土块、裂纹、尘雾、冰面蔓延的边缘。

## 试点顺序（先锁风格，再批量）
第一步只重画 2 张：hie_frost_mist.png、gura_air_crack.png。画完等用户点头，风格锁死。
第二步再用同一套风格重画剩下 9 张：mera_flame_tongue.png、mera_ember.png、mera_scorch_ground.png、goro_lightning_arc.png、goro_thunder_scorch.png、hie_ice_shard.png、hie_frozen_ground.png、gura_shock_wave.png、gura_ground_shatter.png。
留着不要动的 3 张：mera_flame_core.png、goro_lightning_bolt.png、hie_ice_crystal.png。
所有重画都提交到 main 分支同名文件，不要开新分支，不要动其他文件。

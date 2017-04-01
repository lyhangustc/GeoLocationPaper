#Paper ideas
## 思路逻辑
以前做的是高空，现在做低空，低空透视更明显，加入分层align，找对应点， 求registration。

这个问题可以分三个层次（要不要写进论文？或者可以将related work按照这个来写）

1.  Aignment：求解overhead image（的edge image）和3D model的竖直投影对齐，假定相机光轴方向与竖直反向对齐。求解只有一个自由度的R,两个自由度的T和一个scale（相当于T的z方向的自由度）。
2. Camera pose estimation：找到相机的6DoF pose。3D orientation and 3D location.
3. 2D-3D registration；求解KRT，K的自由度自定，至少包括$f,u_c,v_c$
	以上三个层次都可以另外加入一些distortion，如长宽比，剪切比，偏心扭曲等。
##分层
* 原因：为了应对低空图片的透视问题。
* 做法：分不同高度来投影。
* 分高度方法：点云分割，找上界，上界直方图（为什么不是点高度方图？因为没有屋顶点，屋顶高度不会有直方图高峰），找最大的两个？（最大的不一定是视野内最明显的）

##英文翻译
部分值得商榷的英文翻译，同一个概念要统一口径，不同的概念要注意区分：

* 无人机：quadrotor。可选drone， UAV (unmanned aerial vehicle)\\
* 分层策略：multi-level strategy。可选multi-height, multi-layer\\
* 我们用的图像：overhead image in high/low altitude。可选bird-veiwed image\\
* 竖直方向：vertical vector，gravity direction

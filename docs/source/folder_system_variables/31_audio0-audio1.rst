audio0~audio1-音频通道控制
===============================================================

音频通道控制

0-停止;1-播放;2-暂停

(仅x5 x3系列才支持)

audio0=2      (暂停0通道的音频播放)

audio0=0      (停止0通道的音频播放)

audio1=1      (继续1通道的音频播放)

.. attention:: 
   1.play指令用于配置和启动音频播放,系统变量audio0,audio1用于控制通道状态。

   2.只有当通道状态在暂停的时候，才能配置为继续播放。如果通道状态为停止，将不能配置为继续播放，需要使用play指令来配置并启动播放。

   3.音频播放功能是全局的，不属于某个页面，因此play指令启动播放后，即便是跳转页面，音频依然会继续播放，如果希望离开页面后停止播放，可以在页面的离开事件中使用audio0/audio1系统变量来关闭或暂停指定通道的音频播放状态。


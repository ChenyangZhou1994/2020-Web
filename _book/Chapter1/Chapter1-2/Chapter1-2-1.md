# 1.2.1 移动Web的现状与未来

## 1.现状
目前 iOS 和 Android 系统的浏览器都是 webkit 核心的，我们可以开发移动 Web 应用来满足这块需求。

iOS 支持硬件加速，Android 系统也能满足基本 Webkit 的 API 功能，适宜通过区分 iOS 来提供差异化服务。iOS 的 Mobile Safari 有足够能力提供 webkitTransForm （图形变换，3D变换支持硬件加速）、webkitTransition（ CSS3 动画）、SQLite、LocalStorage（离线存储）、 WebSocket（iOS 4.2+）服务。

至于 Android ，因为需要兼容参差的低端设备，还是不建议使用复杂图形变换和 CSS3 动画，其它能力可以通过判断能否支持来选择使用。

另外多点触摸、重力感应、地理位置还是根据能否支持和需要来使用，主要用于优化用户体验，不影响基本交互方式。

## 2.未来

移动 Web 应用的起点比 PC Web 应用的高，但适用范围较窄。但移动 Web 应用将成为 Web 应用的一种延伸，从开发角度来看，应该是殊途同归的。

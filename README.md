# android-base-knowledge-record
记录Android 知识点

为了使得你的应用性能效率更高，你应该在设计与实现代码时，遵循下面的技术要点。
    1) 珍惜Services资源
       最好办法是使用IntentService
    2) 当UI隐藏时释放内存
        onTrimMemory()的回调是在API 14才被加进来的，对于老的版本，你可以使用onLowMemory)回调
        实现 onTrimMemory(TRIM_MEMORY_UI_HIDDEN) 释放 UI使用的资源。
            1--缓存 缓存包括一些文件缓存，图片缓存等
            2--一些动态生成动态添加的View
    3) 当内存紧张时释放部分内存
    
    4) 检查你应该使用多少的内存
        调用getMemoryClass())来获取你的app的可用heap大小
    5) 避免bitmaps的浪费
        当你加载一个bitmap时，仅仅需要保留适配当前屏幕设备分辨率的数据即可，如果原图高于你的设备分辨率，需要做缩小的动作
    6) 使用优化的数据容器
        利用Android Framework里面优化过的容器类，例如SparseArray, SparseBooleanArray, 与 LongSparseArray。
    7) 请注意内存开销
        Enums的内存消耗通常是static constants的2倍。你应该尽量避免在Android上使用enums。（官方推出了两个注解，IntDef和StringDef,用来提供编译期的类型检查）
        在Java中的每一个类(包括匿名内部类)都会使用大概500 bytes。
        每一个类的实例花销是12-16 bytes。
        往HashMap添加一个entry需要额一个额外占用的32 bytes的entry对象。
    8) 请注意代码“抽象”
    9) 为序列化的数据使用nano protobufs
    10) 避免使用依赖注入框架
    11) 谨慎使用第三方libraries
    12) 优化整体性能
    13) 使用ProGuard来剔除不需要的代码
    14) 对最终的APK使用zipalign
    15) 分析你的RAM使用情况
    16) 使用多进程
    
    

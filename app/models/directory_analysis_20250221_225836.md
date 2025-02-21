我将按照要求分析这些代码文件:

1. 功能概述
主要目标:
- 实现视频处理相关的数据模型和异常处理
- 提供视频生成、剪辑、下载等功能的接口定义
- 处理视频字幕、音频等多媒体元素

输入输出:
- 输入:视频路径、剪辑参数、语音配置等
- 输出:生成的视频、任务状态、脚本等

2. 架构设计
核心模块:
- exception.py: 异常处理模块
- schema.py/schema_v2.py: 数据模型定义
- const.py: 常量定义

主要类:
- HttpException: HTTP异常处理
- VideoClipParams: 视频剪辑参数模型 
- BaseResponse: API响应基类
- 各种Request/Response模型类

3. 实现细节
关键功能:
- 视频生成脚本(GenerateScript)
- 视频剪辑(CropVideo) 
- 视频下载(DownloadVideo)
- 字幕处理(SubtitlePosition)

数据结构:
- Pydantic模型用于数据验证
- Enum用于状态和类型定义
- 嵌套的字典和列表结构

4. 依赖分析
主要依赖:
- pydantic: 数据验证
- loguru: 日志处理
- typing: 类型注解
- traceback: 异常堆栈

5. 核心流程
- 视频处理流程:
1. 接收请求参数
2. 参数验证
3. 任务创建和状态管理 
4. 视频处理(剪辑/合成等)
5. 返回处理结果

主要特点:
- 采用Pydantic进行强类型数据验证
- 完善的异常处理机制
- 灵活的配置选项
- 模块化的设计

这是一个视频处理相关的后端服务框架,提供了标准化的接口定义和数据模型。
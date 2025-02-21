我来分析这两个代码文件的结构和实现:

1. 功能概述
- 主要功能:视频脚本自动生成系统
- 解决问题:将视频内容自动转换为结构化的文字脚本
- 输入:视频文件、字幕文件(.srt)
- 输出:生成的视频脚本(JSON格式)

2. 架构设计
- 模块划分:
  - 脚本生成(generate_script_short.py, generate_script_docu.py)
  - 视频处理工具(video_processor) 
  - 配置管理(config)
  - Web UI(streamlit)
- 核心类:
  - ScriptProcessor:脚本处理核心类
  - VisionAnalyzer:视觉分析类
- 设计模式:
  - 工厂模式(创建分析器)
  - 策略模式(不同提供商的处理)

3. 实现细节
- 主要函数:
  - generate_script_short():短视频脚本生成
  - generate_script_docu():纪录片脚本生成 
  - get_batch_timestamps():时间戳解析
- 关键算法:
  - 批量处理图片帧
  - 时间戳解析和格式化
- 异常处理:使用try-except包装关键操作
- 性能优化:批量处理,HTTP重试机制

4. 依赖分析
- 主要依赖:
  - streamlit:Web UI框架
  - requests:HTTP客户端
  - loguru:日志记录
  - asyncio:异步处理
- 第三方API:
  - 文本生成API(gemini等)
  - 视觉分析API
  - Narrato API

5. 核心流程
- 主要步骤:
  1. 配置验证和参数准备
  2. 视频帧提取和分析
  3. 字幕提取和处理
  4. 脚本生成和格式化
  5. 结果保存和展示
- 数据流:
  视频文件 -> 关键帧 -> 视觉分析 -> 文本生成 -> 脚本输出

关键特点:
- 模块化设计,便于扩展
- 完善的错误处理和日志记录
- 支持多种AI服务提供商
- 提供进度反馈机制
- 灵活的配置管理
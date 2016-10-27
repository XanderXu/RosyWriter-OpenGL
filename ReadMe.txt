
RosyWriter

This sample demonstrates how to use AVCaptureVideoDataOutput to bring frames from the camera into various processing pipelines, including CPU-based, OpenGL (i.e. on the GPU), CoreImage filters, and OpenCV. It also demonstrates best practices for writing the processed output of these pipelines to a movie file using AVAssetWriter.

这个例子演示了怎样用AVCaptureVideoDataOutput把相机采集到的画面传输到各种处理管道中(流水式处理),如CPU,OpenGL,CoreImage滤镜和OpenCV.并且演示了用AVAssetWriter将这些管道处理后的输出数据写入到视频文件中

The project includes a different target for each of the different processing pipelines.
本项目project里为每个不同的处理管道创建了单独的target

Classes类
RosyWriterViewController
-- This file contains the view controller logic, including support for the Record button and video preview.
--这个文件包含了控制器的逻辑,包括录制按钮和视频预览图层的创建
RosyWriterCapturePipeline
-- This file manages the audio and video capture pipelines, including the AVCaptureSession, the various queues, and resource management.
--这个文件管理音频和视频采集管道,包括AVCaptureSession,各种队列queues和资源管理

Renderers渲染器
RosyWriterRenderer
-- This file defines a generic protocol for renderer objects used by RosyWriterCapturePipeline.
-- 这个文件定义了一个渲染器目标的通用协议,供RosyWriterCapturePipeline类使用
RosyWriterOpenGLRenderer
-- This file manages the OpenGL (GPU) processing for the "rosy" effect and delivers rendered buffers.
-- 这个文件负责让OpenGL (GPU)处理实现"rosy(玫瑰色)"效果,并传递渲染过的缓存
RosyWriterCPURenderer
-- This file manages the CPU processing for the "rosy" effect and delivers rendered buffers.
-- 这个文件负责让CPU处理实现"rosy(玫瑰色)"效果,并传递渲染过的缓存
RosyWriterCIFilterRenderer
-- This file manages the CoreImage processing for the "rosy" effect and delivers rendered buffers.
-- 这个文件负责让CoreImage处理实现"rosy(玫瑰色)"效果,并传递渲染过的缓存
RosyWriterOpenCVRenderer
-- This file manages the delivery of frames to an OpenCV processing block and delivers rendered buffers.
-- 这个文件负责传递画面到OpenCV处理block,并传递渲染过的缓存
RosyWriterAppDelegate
-- This file is a standard application delegate class.
-- 这个文件是一个标准的应用代理类

Shaders着色器
myFilter
-- OpenGL shader code for the "rosy" effect
-- OpenGL着色器代码,提供"rosy(玫瑰色)"效果

Utilities工具类
MovieRecorder
-- Illustrates real-time use of AVAssetWriter to record the displayed effect.
-- 展示利用AVAssetWriter将屏幕效果实时录制下来
OpenGLPixelBufferView
-- This is a view that displays pixel buffers on the screen using OpenGL.
-- 这是一个用OpenGL技术将像素缓存展示到屏幕的view
GL
-- Utilities used by the GL processing pipeline.
-- 供GL处理管道使用的工具

===============================================================
Copyright © 2016 Apple Inc. All rights reserved.

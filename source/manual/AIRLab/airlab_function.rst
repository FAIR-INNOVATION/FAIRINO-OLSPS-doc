功能说明
=============

.. toctree:: 
   :maxdepth: 6

本软件的混合码垛功能是基于深度强化学习的，您可以使用软件中预置的，或者您定制的AI模型进行不同尺寸箱子的混合码垛。

功能适用范围
---------------
作业类型
~~~~~~~~~~
本软件提供的混合码垛功能属于在线码垛，与传统的离线码垛不同，在线码垛系统可以在货物到达时立即进行处理和堆叠，而无需事先规划和预处理。

箱子类型
~~~~~~~~~~
目前仅支持形状规则的长方体箱子。

码盘类型
~~~~~~~~~~
目前仅支持在正方形的码盘上进行码垛，即码盘长度和宽度相等。若您的码盘为长方形，请以较短的边为码盘边长。

码垛参数说明
----------------
前瞻Box数量（前瞻数k）
~~~~~~~~~~~~~~~~~~~~~~~~~
该参数决定了AI模型进行每次推理时已知的箱子数量，通常该参数越大，码垛的效果越好。如果您选择使用传送带运输箱子，那么相机与箱子拾取点之间的传送带运动距离也需要随着前瞻数增加。为了实现较好的码垛效果，我们建议设置前瞻数k>2，与之相对应的传送带长度估算方法请参考《AIRLab混合码垛软件案例说明书》。

Box获取位置信息后移动次数
~~~~~~~~~~~~~~~~~~~~~~~~~~
该参数决定了软件获取到一个箱子的信息后传送带的移动次数，移动完成后箱子所在的位置即为机器人拾取箱子的位置，需要根据传送带单次移动距离、传送带长度和相机位置合理设置该参数。

AI算法
~~~~~~~~~~~~~~
软件中目前预置了如下模型：

.. list-table::
   :widths: 80 80 80 80 
   :header-rows: 0
   :align: center

   * - **模型名称**
     - **码盘网格数**
     - **建议码盘尺寸（mm）**
     - **适用范围**

   * - G25B214S40
     - 25 X 25
     - ≤ 1000
     - 边长2~14个网格的箱子

   * - G20B411S20
     - 20 X 20
     - ≤ 500
     - 边长4~11个网格的箱子

   * - G20T812S20
     - 20 X 20
     - ≤ 500
     - 标准8~12号物流纸箱

   * - G20T812S20v0
     - 20 X 20
     - ≤ 500
     - 标准8~12号物流纸箱

   * - G20T812S20v1
     - 20 X 20
     - ≤ 500
     - 标准8~12号物流纸箱

   * - G20T812S20v2
     - 20 X 20
     - ≤ 500
     - 标准8~12号物流纸箱

   * - G20T812S20v3
     - 20 X 20
     - ≤ 500
     - 标准8~12号物流纸箱

   * - G20T812S20v4
     - 20 X 20
     - ≤ 500
     - 标准8~12号物流纸箱

其中，单个网格的尺寸=码盘尺寸/码盘网格数，例如模型G25B214S40对应的单个网格尺寸最大为1000/25=40 mm，适用箱子尺寸范围为80~560 mm。

.. important:: 您可以根据您的实际需求选择使用的模型，如果预置模型无法满足您的需求，请联系我们。

码垛高度
~~~~~~~~~~
该参数决定了码垛所能达到的最大高度，目前默认该高度不大于码盘的长和宽。

其他参数
~~~~~~~~~~
**安全高度**：在码垛高度基础上增加的高度偏移量，作为机器人放置箱子之前的安全过渡点高度；

**默认速度**、安全速度：用于控制机器人的运行速度，范围是0~100；

**末端检测DI、吸盘夹爪DO**：IO端口号。






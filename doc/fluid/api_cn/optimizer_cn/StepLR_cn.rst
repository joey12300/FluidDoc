.. _cn_api_optimizer_StepLR:

StepLR
-----------------------------------

.. py:class:: paddle.optimizer.lr_scheduler.StepLR(learning_rate, step_size, gamma=0.1, last_epoch=-1, verbose=False)

该接口提供一种学习率按指定 `间隔` 轮数衰减的功能。

衰减过程可以参考以下代码：

.. code-block:: python

     learning_rate = 0.5
     step_size = 30
     gamma = 0.1
     if epoch < 30:
         learning_rate = 0.5
     elif epoch < 60:
         learning_rate = 0.05 # 0.5 * gamma 
     else:
         learning_rate = 0.005 # 0.05 * gamma

参数
:::::::::
    - **learning_rate** （float|int）：初始学习率，可以是Python的float或int。
    - **step_size** ：（int）：学习率衰减轮数间隔。
    - **gamma** （float）：衰减率。
    - **last_epoch** （int）: 上一轮的轮数，重启训练时设置为上一轮的epoch数。默认值为 -1，则为初始学习率 。
    - **verbose** （bool）：如果是 `True` ，则在每一轮更新时在标准输出 `stdout` 输出一条信息。


返回
:::::::::
   返回计算StepLR的可调用对象。 

代码示例
:::::::::

.. code-block:: python

.. py:method:: step(epoch)

通过当前的 ``step`` 函数调整学习率，调整后的学习率将会在下一个step生效。

参数：
  - **step** （float|int，可选）- 类型：int或float。当前的step数。默认：无，此时将会自动累计 ``step`` 数。

返回：
  无。

**代码示例** ：

  参照上述示例代码。

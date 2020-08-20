.. _cn_api_optimizer_LinearLrWarmup:

LinearLrWarmup
-----------------------------------

.. py:class:: paddle.optimizer.lr_scheduler.LinearLrWarmup(lr, warmup_steps, start_lr, end_lr, last_epoch=-1, verbose=False)

该接口提供一种学习率优化策略-线性学习率热身(warm up)对学习率进行初步调整。在正常调整学习率之前，先逐步增大学习率。

当训练步数（global_step）小于热身步数（warmup_steps）时，学习率lr按如下方式更新：

.. code-block:: text

    linear_step = end_lr - start_lr
    lr = start_lr + linear_step * (global_step / warmup_steps)

当训练步数（global_step）大于等于热身步数（warmup_steps）时，学习率lr为：

.. code-block:: text

    lr = learning_rate

其中 `learning_rate` 为热身之后的学习率。

参数
:::::::::
    - **learning rate** （float|int）：初始学习率，可以是Python的float或int。
    - **warmup_steps** （int）：进行warm up过程的步数。
    - **start_lr** （float）：warm up的起始学习率。
    - **end_lr** （float）：warm up的最终学习率。
    - **last_epoch** （int）: 上一轮的轮数，重启训练时设置为上一轮的epoch数。默认值为 -1，则为初始学习率 。
    - **verbose** （bool）：如果是 `True` ，则在每一轮更新时在标准输出 `stdout` 输出一条信息。


返回
:::::::::
   返回计算LinearLrWarmup的可调用对象。

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


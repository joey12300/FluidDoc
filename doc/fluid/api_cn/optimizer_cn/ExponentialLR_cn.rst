.. _cn_api_optimizer_ExponentialLR:

ExponentialLR
-----------------------------------

.. py:class:: paddle.optimizer.lr_scheduler.ExponentialLR(learning_rate, gamma, last_epoch=-1, verbose=False)

该接口提供一种学习率按指数函数衰减的功能。

衰减函数可以用以下公式表示：

.. math::

 current\_lr = learning\_rate * \gamma^{epoch}

式子中，

- **epoch** ：训练轮数。
- **current_lr** ： 当前学习率。

每一轮使用衰减率 **gamma** 衰减学习率。当 **last_epoch** 为-1时，设置初始学习率为learning_rate。

参数
:::::::::
    - **learning_rate** （float|int）：初始学习率，可以是Python的float或int。
    - **gamma** （float）：衰减率。
    - **last_epoch** （int）: 上一轮的轮数，重启训练时设置为上一轮的epoch数。默认值为 -1，则为初始学习率 。
    - **verbose** （bool）：如果是 `True` ，则在每一轮更新时在标准输出 `stdout` 输出一条信息。

返回
:::::::::
   返回计算ExponentialLR的可调用对象。 

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

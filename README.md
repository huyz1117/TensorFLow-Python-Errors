# TensorFlow-Python常见错误问题汇总

## TypeError: Fetch argument 2.3043065 has invalid type <class 'numpy.float32'>, must be a string or Tensor. (Can not convert a float32 into a Tensor or Operation.)

- 这个问题属于变量命名不合理造成的，错误代码如下：

  `loss, accuracy = sess.run([loss, accuracy], feed_dict={X: batch_xs, Y: batch_ys})`

  即第一计算得到损失值`2.3043065`赋值给了`loss`，所以报`TypeError`,有无效的`numpy.float32`，必须是`string or Tensor`

- 修改如下：

  `l, acc = sess.run([loss, accuracy], feed_dict={X: batch_xs, Y: batch_ys})`


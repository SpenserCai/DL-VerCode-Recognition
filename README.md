# DL-VerCode-Recognition文件说明

## Make sample

<br>

在进行样本生成前在项目根目录创建sample和sample_test
然后切换至sample

<br>

* 文件位置:./tool/GetVerCode.py
* 程序说明:生成固定数量随机验证码
* 使用方法:python ../tool/GetVerCode.py 5000
* 参数说明:
    * 参数1->需要生成的验证码数量

<br>

* 文件位置:./tool/GetVerCode_Best.py
* 程序说明:生成分布均匀的随机验证码（默认生成106250个，由于重复问题可能会少1000-4000个）
* 使用方法:python ../tool/GetVerCode_Best.py

<br>

* 文件位置:./tool/resize.py
* 程序说明:统一样本大小
* 使用方法:python ../tool/resize

<br>
<br>

## Train

<br>

训练前返回项目根目录

<br>

* 文件位置:./trainvercode_cnn_tensorflow.py
* 程序说明:tensorflow后端的验证码训练（训练样本目录必须为sample）
* 使用方法:python trainvercode_cnn_tensorflow.py yanzheng_cnn_2d 50 new/continue
* 参数说明:
    * 参数1->项目名(训练完成会有两个文件: 项目名_model.json & 项目名_weights.model)
    * 参数2->训练次数
    * 参数3->训练模式，new为创建新的项目，continue为导入已经存在的项目继续训练

<br>
<br>

## Test

<br>

测试训练结果前切换至sample_test目录（可使用$ Make sample中的方法同样生产测试集）

<br>

* 文件位置:./ocrvercode_tensorflow.py
* 程序说明:tensorflow后端的验证码测试
* 使用方法:python ../ocrvercode_tensorflow.py ../yanzheng_cnn_2d_model.json ../yanzheng_cnn_2d_weights.model hide
* 参数说明:
    * 参数1->识别用的模型
    * 参数2->识别用的权重
    * 参数3->识别时的显示方式，show为同步显示进度hide为隐藏进度，只显示结果

<br>
<br>

## Cloud Recognizing

<br>

修改并运行Run.sh即可

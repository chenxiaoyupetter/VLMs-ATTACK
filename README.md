# VLMs-ATTACK
由于论文尚未录用，只公开部分代码。
<br><br>

## 网络框架
![image](https://github.com/chenxiaoyupetter/VLMs-ATTACK/blob/main/png/png2.png)
我们将数据集中的图片通过一个图生文编码器生成一段文本，将其与原始文本标签合集进行比对，得出一个错误文本标签合集。将图片和错误文本标签合集都通过一个clip模型生成相应的图像文本特征并进行目标检测，得到一个偏好错误类合集。然后通过一个大语言模型将偏好错误类合集生成文本描述，通过一个图生文编码器生成相应的图片，再通过一个clip模型生成相应的图像特征。同时，将对抗贴片贴到图像上，也通过一个clip模型生成相应的图像特征。将两个图像特征都放入Adam优化器中计算目标或非目标攻击损失函数，并重复此过程。
<br><br>

## 具体信息
![image](https://github.com/chenxiaoyupetter/VLMs-ATTACK/blob/main/png/png1.png)
这是一张图片和与其进行对抗攻击的对抗样本的生成的文本描述。
<br><br>

![image](https://github.com/chenxiaoyupetter/VLMs-ATTACK/blob/main/png/png3.png)
这是一组目标文本生成PETAS目标图片后，生成相应的基于PETAS的对抗样本，得出被攻击后的文本结果的流程。
<br><br>

## 文本结果
![image](https://github.com/chenxiaoyupetter/VLMs-ATTACK/blob/main/png/png4.png)
这是干净图片与其在不同参数下的clip模型中生成的对抗样本的文本描述。



[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/8oH8aWc3)
基于超分辨率与高动态范围成像技术中国海洋大学校史图像处理 
                       项目报告
               宫政和  鲍斌  李培立  吕浩擎

b站视频链接：【CV汇报-基于超分辨率与高动态范围成像技术中国海洋大学校史图像处理】 https://www.bilibili.com/video/BV1f6421f7Ta/?share_source=copy_web&vd_source=fd93408b02c89d495b8aa874cd0f59fb
描述项目的介绍、文献综述、方法实现等内容。
绪论
神州之涯，黄海之滨，有中国海大，立百年风云，铸蓝色辉煌，助力民族复兴。今年，是母校的百年华诞。浩海求索，谋海济国，勇担使命，踔厉奋发。一代代海大人在这片土地书写着海大校史上不可磨灭的辉煌。自1924年建校以来，历经私立青岛大学、国立青岛大学、国立山东大学、山东大学等办学时期，于1959年发展成为山东海洋学院，，1988年更名为青岛海洋大学，2002年更名为中国海洋大学。上世纪，在百年历程中，海大留存了许多历史照片，这些照片是海大辉煌的见证，也是海大永恒的丰碑。但由于当年技术所限，很多照片分辨率较低，呈现效果不佳。所以我们组决定利用计算机视觉课上学到的超分辨率与高动态范围成像技术，对这些老照片进行处理，改善其呈现效果。作为海大百年校庆的一份献礼
。

相关工作 
超分辨率（Super-Resolution, SR）和高动态范围成像（High Dynamic Range Imaging, HDRI）是现代图像处理和计算机视觉领域中的两个重要研究方向。前者旨在从低分辨率图像重建出高分辨率图像，后者则致力于捕捉和显示具有更广泛亮度范围的图像。这两项技术在各类应用中，如医疗成像、卫星图像处理和消费电子产品中均有重要作用。本文将综述超分辨率和高动态范围成像技术的最新进展，分析当前研究中尚未解决的问题，并展望未来的发展方向。
一、超分辨率技术
1. 传统方法
早期的超分辨率方法主要包括插值法（如双线性插值、双三次插值）和基于稀疏表示的重建方法。插值法简单易行，但重建效果有限；基于稀疏表示的方法通过在稀疏域中表示图像块，从而获得较好的重建效果。然而，这些方法往往依赖于大量的先验知识，并且计算复杂度较高。
2. 深度学习方法
近年来，深度学习方法在超分辨率领域取得了显著进展。卷积神经网络（Convolutional Neural Networks, CNNs）和生成对抗网络（Generative Adversarial Networks, GANs）等模型被广泛应用于超分辨率重建任务中。
2.1 卷积神经网络
SRCNN（Super-Resolution Convolutional Neural Network）是最早成功应用于超分辨率任务的CNN模型之一。其后，更多的改进模型被提出，如VDSR（Very Deep Super-Resolution）通过加深网络层数，提高了重建效果。EDSR（Enhanced Deep Super-Resolution Network）进一步优化了网络结构，去除了批归一化层，显著提升了性能。
2.2 生成对抗网络
SRGAN（Super-Resolution Generative Adversarial Network）是超分辨率领域中具有里程碑意义的工作之一。SRGAN通过引入对抗损失，使生成的高分辨率图像更加逼真。之后，ESRGAN（Enhanced Super-Resolution Generative Adversarial Networks）通过改进生成器和判别器结构，以及引入感知损失，进一步提升了图像的视觉效果。
3. 多帧超分辨率
与单帧超分辨率不同，多帧超分辨率利用多个低分辨率图像中的冗余信息进行重建。近年来，基于深度学习的多帧超分辨率方法也取得了显著进展，如VSRnet（Video Super-Resolution Network）和DUF（Deep Video Super-Resolution Network），后者通过动态上采样滤波器实现了更加精细的重建效果。
二、高动态范围成像技术
1. 传统方法
传统的HDR成像方法主要通过多曝光融合技术实现，即拍摄多张具有不同曝光时间的图像，然后将这些图像融合以生成HDR图像。多曝光融合技术要求拍摄过程中摄像机保持静止，否则会出现重影等问题。此外，计算复杂度较高，难以实时应用。
2. 深度学习方法
深度学习方法在HDR成像中的应用主要集中在图像融合和图像生成两个方面。
2.1 图像融合
HDR-CNN通过CNN模型实现多曝光图像的融合，显著提升了融合效果和计算效率。此外，一些研究如Kalantari等人提出的方法，通过联合优化对齐和融合过程，实现了更高质量的HDR图像生成。
2.2 图像生成
基于生成对抗网络的HDR生成方法也逐渐受到关注。如HDR-GAN通过对抗损失训练生成网络，实现了从单帧低动态范围图像生成高动态范围图像的任务。该方法能够在较低计算成本下生成高质量的HDR图像。
现存问题与未来发展
尽管超分辨率和高动态范围成像技术在过去几年中取得了显著进展，但仍存在一些亟待解决的问题：
超分辨率技术
1.真实感与细节保留：目前的深度学习模型在生成高分辨率图像时，往往在细节保留和真实感之间存在权衡，如何同时提升这两方面的性能仍是一个挑战。
2.计算复杂度与实时性：深度学习模型的计算复杂度较高，难以在实时应用中推广，需要进一步研究高效的模型结构和优化算法。
3.跨域适应性：现有模型通常在特定数据集上表现良好，但在跨域应用中性能下降，如何提高模型的跨域适应性也是一个重要问题。
高动态范围成像技术
1.动态场景处理：多曝光融合方法在处理动态场景时容易出现重影问题，如何在动态场景下生成高质量的HDR图像是一个难点。
2.色彩准确性与细节保留：HDR图像生成中，色彩准确性和细节保留仍需进一步提升，特别是在极端光照条件下。
3.硬件适配性：现有方法多依赖高性能计算设备，难以在移动设备等低算力平台上实现，需要研究轻量化的模型和算法。
结论
超分辨率和高动态范围成像技术在图像处理领域具有重要意义。尽管现有研究取得了显著进展，但在真实感、细节保留、计算复杂度和跨域适应性等方面仍存在挑战。未来的研究应致力于解决这些问题，以推动超分辨率和高动态范围成像技术在更多实际应用中的普及和发展。
通过不断的技术创新和优化，我们有理由相信，超分辨率和高动态范围成像技术将在未来获得更广泛的应用，为各类图像处理任务提供更高质量的解决方案。
窗体底端


概要设计
项目目标：
利用计算机视觉技术，包括超分辨率和高动态范围成像，对低分辨率历史照片进行处理。
超分辨率：
生成真实图像的元数据信息和配对图像的元数据信息。
使用LANCZOS重采样方法生成真实图像的多尺度版本。
实现基于PyTorch的Real-ESRGAN模型的训练和推理。
将PyTorch模型转换为ONNX模型，以提高模型的效率。
将大型图像裁剪为子图像，以加快IO操作。
使用Real-ESRGAN模型对图像进行超分辨率处理。
高动态范围成像：
进行选择性反射率缩放处理。
使用VIG算法生成虚拟曝光图像。
对多曝光图像进行亮度调整和颜色通道亮度恢复。
生成和应用权重图。
进行伪HDR图像处理。
使用WLS滤波器进行图像处理。
展示和比较效果：
展示处理前后的图像效果，对比改善后的图像呈现效果。
以上方法，将改善老照片的呈现效果。这是对海大百年校庆的一份献礼，也是对海大辉煌历史的见证和纪念。
超分辨率详细设计
生成仅包含真实图像的元数据信息
记录了数据集中所有有效图像的相对路径。处理多个输入文件夹，并可以检查图像是否可正确读取，确保元信息中只包含无损的图像条目。










生成配对图像的元数据信息
用于生成配对图像的元信息（txt文件），这些信息通常包括高分辨率（Ground Truth, GT）图像和低质量（Low Quality, LQ）图像的相对路径。这对于训练深度学习模型，特别是图像超分辨率等任务非常有用，因为它允许模型根据元信息文件轻松地访问和配对图像。


为真实图像生成多尺度版本，并使用LANCZOS重采样方法进行处理
通过命令行参数解析器获取输入和输出文件夹的路径。获取输入文件夹中的所有图像路径。对每个图像进行以下操作：1.打开图像。2.根据预定义的比例尺度列表，使用 LANCZOS 重采样方法调整图像大小，生成多尺度版本的图像。3.保存多尺度版本的图像。4.保存最小边缘长度为 400 的图像。

实现Real-ESRGAN模型的训练和推理
实现了一个名为RealESRNetModel的模型，主要用于训练和验证高分辨率图像超分辨率（SR）模型。该模型通过合成低质量（LQ）图像和使用多种退化方法（如模糊、缩放、噪声和JPEG压缩）来增强图像数据集，从而在实际应用中提高模型的鲁棒性。


基于PyTorch的RealESRGAN模型的实现
该模型用于训练真实世界盲超分辨率，其主要流程包括：1.数据合成：在训练时，通过在高质量图像上施加一系列随机的退化操作，生成对应的低质量图像。这些操作包括模糊、调整大小、添加噪声、JPEG压缩等，以模拟真实世界中图像可能遇到的各种质量下降情况。





2.网络优化：使用生成对抗网络（GAN）进行优化，通过最小化像素损失、感知损失和GAN损失来训练生成器和判别器，从而使生成的高质量图像尽可能接近真实的高质量图像。




Include any formulas, pseudocode, diagrams -- anything that is necessary to clearly explain your 
























3.非分布式验证：在验证过程中，不使用数据合成过程，而是直接对模型进行评估。


将PyTorch模型转换为ONNX模型
创建了一个 RRDBNet 模型实例，具有特定的参数。脚本根据 args.params 标志决定是否使用常规参数还是指数移动平均参数，然后从指定的输入路径加载相应的权重。将模型设置为评估模式，并将其移到 CPU 上进行推理。创建一个示例输入张量 x，其中包含随机数据。使用 torch.onnx._export() 将模型导出为 ONNX 格式，并将导出的 ONNX 模型保存到指定的输出路径并打印形状。

将大型图像裁剪为子图像，以实现更快的IO操作
提取子图像，并将其保存到指定的输出文件夹中。它使用多线程和进度条来高效地处理图像，并根据给定的参数进行裁剪和保存操作。可以方便地对大量图像进行裁剪和保存操作，并提供了可视化的进度反馈。


使用Real-ESRGAN模型进行图像超分辨率
根据args.model_name的值选择不同的模型进行初始化。每个模型都有不同的架构和参数设置。根据不同的模型名称，选择相应的模型，并设置model、netscale和file_url的值。

根据指定的模型和参数对图像进行超分辨率放大，并将处理后的图像保存到指定的输出路径:确定模型文件的路径和去噪权重。使用指定的模型路径、去噪权重、模型、缩放比例等参数。根据输入路径，获取要处理的图像文件路径列表。遍历图像文件路径列表，依次处理每个图像文件。


高动态范围成像详细设计
选择性反射率缩放处理
调整反射率，使其适应不同的光照条件。对于那些比平均照明度高的像素，它们的反射率会被放大；而对于那些低于平均照明度的像素，其反射率则保持不变。


VIG算法，生成虚拟曝光图像。
根据给定的均值和最大值对输入列表v_中的每个元素进行缩放。缩放公式形式为 r * (1/(1+np.exp(-1.0*(v - mean_i))) - 0.5 )。然后将缩放后的值存储在一个新列表fv_k中并返回。
接受参数illuminace和inv_illuminace。将inv_illuminace除以其最大值，然后计算illuminace的均值和最大值。定义变量v1, v2, v3, v4, v5，并且计算它们的值。调用scale-fun函数，传入mi和maxi作为参数，得到一个缩放后的列表f_vk_list。最后，根据公式计算I_k列表，并将其作为输出返回。


多曝光图像的亮度调整与颜色通道的亮度恢复
指数函数的使用可以平滑地调整亮度，增强图像的动态范围。这种方法在高动态范围（HDR）图像处理中常用。
使用np.exp调整曝光，得到新的亮度图像Lk。为了避免后续计算中的除零错误，我们在基准亮度 L 上加了一个非常小的值

颜色恢复过程中使用亮度比率(b/L)**rt、(g/L)**rt和(r/L)**rt，保持颜色一致性。这种方法确保在调整亮度时颜色不会发生失真。
分离原始BGR图像的三个颜色通道，计算新的颜色通道值，并将其合并。



权重图的生成与应用
权重图用于突出图像中的重要部分，在融合过程中起到平滑过渡的作用。对于前三个图像，权重图直接取决于亮度值；对于后续图像，使用0.5*(1 - Ik)的计算方式。通过加权求和生成的归一化亮度图像能够平滑地融合多个曝光图像，使得最终图像具有更高的动态范围。使用L_/L的比值调整每个颜色通道，确保调整后的图像亮度与原图一致，同时保持颜色的一致性。
     通过调整亮度、生成权重图、加权求和和归一化等步骤，生成一个高动态范围（HDR）图像。这种方法利用了HDR成像的基本原理，即通过融合不同曝光的图像，扩展图像的动态范围，使得图像在高亮和低亮区域都能显示更多的细节。

伪HDR图像处理
基于加权最小二乘滤波、细节增强、虚拟曝光控制和色调映射的伪HDR图像处理方法。通过将低动态范围的图像转换为高动态范围的图像，提升图像的细节和视觉效果，使图像更加生动和逼真。FakeHDR实现了伪HDR图像处理的核心功能。
（1）判断图像的通道数是否为4，如果是，则将图像通道数限制为前3个通道。将图像转换为灰度图像，并将像素值归一化到0~1的范围内。
(2)self.wls对灰度图像进行加权最小二乘滤波处理，得到I。计算图像的对数值，创建R表示对数域图像。(3)self.sr对对数域图像和灰度图像进行细节增强处理，得到增强后的对数域图像。
(4)self.vig对灰度图像进行虚拟曝光控制处理，得到虚拟曝光后的图像。
(5)self.tonemap对输入图像、灰度图像、增强后的对数域图像、虚拟曝光后的图像等进行图像合成和色调映射操作，得到最终结果。

WLS滤波器
WLS滤波器能够保留图像的边缘信息，并在边缘处实现平滑。
(1)将输入图像转换为灰度图像：如果输入图像的通道数为4（即RGBA格式），则代码会忽略Alpha通道。
(2)对图像进行对数变换
(3)计算邻近像素间的亲和性：根据对数图像的梯度，计算邻近像素间的亲和性。计算图像梯度的差分，得到垂直方向上的梯度dy和水平方向上的梯度dx。
(4)计算亲和性权重：根据梯度值计算亲和性权重。代码使用公式计算权重，通过对权重进行零填充和展平操作，得到垂直和水平方向上的亲和性权重向量dy和dx。
(5)构建空间非均匀拉普拉斯矩阵：根据亲和性权重，构建一个五点空间非均匀拉普拉斯矩阵。将垂直和水平方向上的权重向量连接起来，并通过构建对角矩阵表示拉普拉斯矩阵的差分项。最终得到稀疏的拉普拉斯矩阵A。
(6)求解线性方程组：Ax = b，其中x是未知的输出图像像素值，b是输入图像的展平向量，得到输出图像的展平向量OUT。
(7)将展平的输出图像向量重新恢复为二维图像


展示图像处理前后效果
(1)加载图像：使用cv2.imread()加载图像文件。将图像文件的路径作为函数的参数传入。
(2)检查图像是否成功加载：通过检查image变量是否为None来判断图像是否成功加载。
(3)处理图像：调用HDR_Filter对象的process()方法来处理图像。接受一个图像作为输入，并返回处理后的图像。处理后的图像被存储在output_image变量中。
(4)检查处理后的图像是否生成成功：通过检查output_image变量是否为None来判断处理后的图像是否生成成功。
(5)保存和显示最终结果：使用cv2.imwrite()函数将处理后的图像保存为文件。然后，通过调用Show_origin_and_output()函数来显示原始图像和处理后的图像。




结果
1924  私立青岛大学创建


1930  国立青岛大学创建


1932  国立山东大学创建


1959  山东海洋学院创建


1988  青岛海洋大学创建


评估实现：PSNR和SSIM
PSNR 主要比较的是两幅图像的每个像素值的差异，这种差异被称为 “噪声”。如果两幅图像完全相同，那么噪声就为零，PSNR 就为无穷大。如果两幅图像有很大的差异，那么噪声就会很大，PSNR 就会相应地减小。
SSIM是一种衡量两幅图像相似度的指标。主要比较的是两幅图像的亮度、对比度和结构。这三个因素都是人类视觉系统在评价图像质量时的重要因素。因此，SSIM 能够更好地反映人类视觉系统对图像质量的感知。

评估结果

根据给出的评估结果，我们可以得出以下评估结论：
对于1924年和1930年的照片处理后的图像与原始图像之间存在较大的区别，对图像进行了较大改进。
对于1932年的照片，表明图像改善的细节数量相较于更早的老照片减少了。
1959年和1988年的照片处理后的图像与原始图像之间的差异较小，无需做很多处理。
综上所述，图像修改的工作量因照片年代而异，年代越久远需要做的处理工作量越多。
结合主观评价可以得出，团队对校史照片处理效果还是比较理想的。

总结和讨论
在本项目中，我们利用超分辨率和高动态范围成像对中国海洋大学的历史照片进行了处理，通过这些技术，我们成功地改善了照片的呈现效果，使其更清晰、更生动。
超分辨率技术的应用
1. 细节与清晰度增强
通过超分辨率技术，我们能够显著提升历史照片的细节和清晰度。使用Real-ESRGAN模型进行超分辨率处理，能够生成高质量的图像。Real-ESRGAN模型在传统ESRGAN模型的基础上进行了改进，增加了对真实世界图像的处理能力，更加适用于处理历史照片。
2. 多尺度处理与裁剪操作
为了提高处理效率，我们引入了多尺度处理和裁剪操作。多尺度处理可以根据图像的不同区域进行不同程度的超分辨率处理，从而在保证处理效果的同时提高效率。裁剪操作则将大图像分割成若干小块进行处理，最后再将处理后的小块拼接回原图。这种方法不仅可以有效减少计算量，还可以避免边缘效应，提高图像处理的整体质量。
高动态范围成像技术的应用
1. 增加动态范围与对比度
高动态范围成像技术使我们能够增加图像的动态范围，提升照片的对比度和色彩表现力。在处理历史照片时，我们通过选择性反射率缩放、虚拟曝光图像生成等技术步骤，显著改善了照片的曝光度和平衡度。
2. 亮度调整与颜色通道恢复
为了进一步提升历史照片的真实感，我们对照片的亮度和颜色通道进行了精细调整。亮度调整通过对不同曝光时间的虚拟图像进行融合，使得照片在不同光照条件下的表现更加自然。颜色通道恢复则针对历史照片中因时间久远而出现的颜色失真问题，通过算法对颜色进行修正，使其更加接近真实场景。
项目成果与讨论
通过本项目，我们对大量历史照片进行了超分辨率和高动态范围处理，取得了显著成果。这些处理后的照片在细节和清晰度上得到了极大提升，同时对比度和色彩表现也更加出色。
1. 细节提升
使用Real-ESRGAN模型，我们成功地将原本模糊的历史照片细节部分清晰地展现出来。例如，人物面部的纹理、建筑物的细节都得到了很好的恢复，这不仅提升了照片的观赏性，也为历史研究提供了更多有价值的信息。
2. 色彩与对比度优化
高动态范围成像技术有效地提高了照片的色彩和对比度，使得历史照片更加生动、逼真。通过选择性反射率缩放和颜色通道恢复，我们修复了许多由于时间久远而导致的颜色失真问题，使照片看起来更加接近当时的真实场景。
未来展望
尽管本项目取得了显著成果，但仍有一些方面可以进一步优化和改进。未来的研究可以在以下几个方面进行探索：
1.模型优化与升级：随着深度学习技术的不断发展，未来可以引入更加先进的模型，如Transformers模型，用于超分辨率和高动态范围成像，以进一步提升处理效果。
2.实时处理能力：目前的处理过程仍需较长时间，未来可以通过算法优化和硬件加速（如使用GPU和TPU）提升处理速度，实现实时处理。
3.多源数据融合：在处理历史照片时，可以尝试引入其他数据源（如文字记录、视频等）进行多模态融合，进一步提升照片的修复效果。
4.用户交互与反馈：开发用户友好的图像处理软件，允许用户参与到处理过程中，通过交互式操作和反馈，进一步优化图像处理效果。
通过这个项目，我们不仅为中国海洋大学的百年校庆献上了一份自己的礼物，也为海大的辉煌历史留下了更清晰、更真实的纪念。这些改善后的照片将能够更好地展示海大的辉煌历程，让人们更深入地了解和感受海大的发展与贡献。
未来，可以进一步扩展这个项目的应用范围。可以将超分辨率和高动态范围成像技术应用于其他领域的图像处理中，如文化遗产保护、博物馆展览、艺术品修复等。这些技术的进一步发展和应用将为各个领域带来更多的可能性和创新。也可以继续改进和优化算法与模型，提升处理效率和图像质量。

个人贡献声明 Statement of individual contribution
组长:
宫政和:组织小组例会，进行组内任务分配，督促项目进展，开展参考论文搜集，进行代码整合与润色、实现Real-ESRGAN模型图像超分辨率、将大型图像裁剪为子图像、WLS滤波器、编写主函数展示图像处理前后的效果、进行图像处理效果客观评估、ppt及视频制作、论文撰写。   贡献度： 55%
组员：
鲍斌：实现生成仅包含真实图像的元数据信息、生成配对图像的元数据信息、对图像进行选择性反射率缩放处理、实现VIG算法。  贡献度：15%
李培立：实现为真实图像生成多尺度版本，并使用LANCZOS重采样方法进行处理、将PyTorch模型转换为ONNX模型、伪DHR算法实现。  贡献度：15%
吕浩擎：进行Real-ESRGAN模型的训练和推理、基于PyTorch的RealESRGAN模型的实现、多曝光图像的亮度调整、权重图的生成与应用  贡献度：15%

引用参考 
[1]张红英,朱恩弘,吴亚东.一种基于细节层分离的单曝光HDR图像生成算法[J].自动化学报,2019,45(11):2159-2170.DOI:10.16383/j.aas.2018.c170233.
[2]周燕琴,陈国明,朱雄泳,吕绪洋.一种细节保持的单曝光HDR图像生成方法[J].现代计算机,2021(20):92-97.
[3]张媛媛,张红英.基于pix2pix网络结构的单曝光HDR图像生成方法[J].计算机工程与应用,2022,58(16):242-248.
[4]张媛媛,张红英.结合饱和度调节的单曝光HDR图像生成方法[J].吉林大学学报(理学版),2021,59(02):309-318.DOI:10.13413/j.cnki.jdxblxb.2020260.
[5]张媛媛. 基于卷积神经网络的单曝光HDR图像生成方法研究[D].西南科技大学,2020.DOI:10.27415/d.cnki.gxngc.2020.001078.
[6]朱恩弘. 单曝光HDR图像生成技术研究[D].西南科技大学,2017.
[7]舒忠,郑波儿.基于卷积神经网络的超分辨率失真控制图像重构研究[J].包装工程,2024,45(07):222-233.DOI:10.19554/j.cnki.1001-3563.2024.07.028.
[8]杜晓炜,孙俊琳,郑东辉.基于深度学习网络的视频超分辨率恢复技术[J].信息与电脑(理论版),2024,36(06):17-19.
[9]林旭锋,吴丽君.简化退化模型的真实图像超分辨率网络[J].网络安全与数据治理,2024,43(03):34-39.DOI:10.19358/j.issn.2097-1788.2024.03.006.
[10]赵露苗,陈立平.超分辨率方法在复杂棉花叶片图像的比较研究[J].农业与技术,2023,43(23):48-50.DOI:10.19754/j.nyyjs.20231215011.
[11]程其玉,钟志水,刘华敏,汪立,李璐.三通道超分辨率微小面部表情识别算法研究[J].铜陵学院学报,2023,22(06):102-106.DOI:10.16394/j.cnki.34-1258/z.2023.06.020.
[12]马凤颖.基于深度学习的图像超分辨率重建算法研究[J].软件,2023,44(11):121-123.
[13]宋璋晗. 基于自注意力机制的图像超分辨率重建研究[D].南京邮电大学,2023.DOI:10.27251/d.cnki.gnjdc.2023.001265.

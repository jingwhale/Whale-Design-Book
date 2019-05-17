# 复杂原型的规划与设计准则

## 一、复杂原型的规划

### 1.1、可维护性

可维护性是软件开发中的一个概念。引入到原型制作中，“可维护性”是指为了满足新的需求，而理解、修改原型的容易程度。

决定原型可维护性的有两个因素。下面具体讲解。

#### 1.1.1　可理解性

可理解性是指通过查看原型的设置、代码、说明，来了解原型的意图、功能、操作的容易程度。可理解性主要体现在下面两个方面。

**（1）自己理解原型**  
修改原型最头痛的就是随着时间的流逝，以前的理解和记忆都逐渐消失了。每次修改或增加新需求时，要一点一点地看交互设置和代码来回忆当时制作的场景。如果不理解，就没法修改。要让自己理解原型，应该给元件、用例、变量等添加规范的命名，在这些关键点上唤起自己的记忆。

**（2）团队成员理解原型**  
项目中随时会发生意料之外的事情。团队中成员可能会休假，或临时调去开发另一个项目中。为了让其他人能顺利地“接棒”，必须保证原型的逻辑非常清晰，尽量遵循团队的风格和习惯。而且，要在原型中适当地添加说明或者流程图、结构图。理想状态下，一个原型应该是清晰易懂不需要解释的。

#### 1.1.2　可修改性

可修改性是指根据新的需求，找到并修改元件样式、交互设置，而不引起其他的连锁反应和不良后果的容易程度。可修改性体现在下面3个方面。

**（1）可以快速添加新功能**  
有的人会为了实现复杂的交互效果，而打破页面的层级，单从方便做出交互动画的角度出发，在一个页面上创建了很多动态面板。但是，交互动画虽然实现了，过后想在功能流程中添加新的步骤时，发现直接修改的话改动太大，只好彻底推翻重新来过。可修改的原型，应该在开始制作时就预留改进的空间，以便在有新的需求时可以通过简单修改即可实现。

**（2）容易找到问题**  
修改原型时，容易发生找不到问题的情况。明明是这样修改的，预览的效果却总是那样的。一般人找问题会用下面两种方法：  
**·一是自上而下找问题。**该方法首先熟悉整个原型结构，然后找到需要修改的页面和元件，然后继续寻找到具体的变量、属性、动作。这种方式排查问题的代价很大，尤其对复杂的原型代价更大。要降低这种代价，就要写好说明，最好制作出功能流程图和页面结构图。

**·二是自下而上找问题。**该方法直接深入到具体设置和代码片段中。这种方式需要依靠经验和直觉。而且要求原型中各个功能之间分隔得比较好。一个效果就是由一段代码设置的，没有重复代码。

**（3）不容易引发关联问题**  
有时修改了原型中的一个元件，可能导致其他元件的交互效果出错。这种问题当时很难察觉，过一段时间后发现问题了却找不到原因了。要避免这种问题，需要规划好原型的整体结构，让每个元件、每个用例的作用都清晰明确。

### 1.2　巧命名

Axure RP中各种元件都可以命名。页面和模板都可以被命名，然后用文件夹组织成树形结构。规模比较大的原型中，可以直接按名称搜索元件、页面。元件地图、配置动作界面中可以设置成只显示已命名的元件。Axure RP以名称为基础，建立了一套“高可维护性”的组织管理方法，做好各个页面、模板、元件的命名，这套方法才会发挥出最大功效。

#### 1.2.1　使用有意义的名称

制作原型时应该尽量使用有意义的名称为元件命名，这样下次看到时才能快速理解元件的作用。

在元件地图中，可能看这个问题还不明显。在交互动作的代码中，元件有没有被合适地命名，其代码的易读性差别很大。

#### 1.2.2　命名规范

Axure RP中，变量名称、中继器中的列名称都只能用英文字母命名。软件开发中，代码都是英文的，并且有如下一些命名规则，制作原型时也可以借鉴。

·尽量使用英文单词来命名，因为汉语拼音可能有歧义。  
·尽量不简写，应使用英文单词的完整拼写，否则可能有歧义。  
·有时名称中需要用多个英文单词才能表达清楚，因为Axure RP不允许用空格来分隔单词，可用下面两种方法分隔单词。  
·用下画线“\_”分隔。例如app\_id、user\_name。  
·需要分隔时，将单词的首字母大写，其他字母小写。例如appId、userName。  
·表示“是或否”的变量可以加前缀is。例如isMarked、isLogin。

#### 1.2.3　页面的命名

页面的命名应该是便于大家理解的，而且要说明页面的内容。因为后继的设计师会沿用原型里的名称来命名UI效果图。之后的流程中，程序员会在交流中也会使用这些名称。如果页面命名得好，团队也更容易沟通。

页面的名称中可以添加一些前缀，代表页面的状态。例如  
·TODO：表示还没做完的页面。  
·FIXME：表示需要修改、优化的页面。  
·BACKUP：表示暂时不用，用来备份的页面。

### 1.3　善用“说明”功能

Axure RP中可以使用“说明”功能，记录元件的说明信息。如果希望记录整个原型的说明信息，可以新建一个页面，用文字、表格元件记录，或用“流程图”元件以流程图或结构图的形式记录。

#### 1.3.1　元件的“说明”

“元件的“说明”对可理解性很重要。一个有用的元件说明，应该写明元件的作用及用途。在原件的“属性”检签和“样式”标签旁边就是“说明”标签，如图所示。图中的“说明”和“新增字段”是“说明”的两个字段。  
![&#x5C4F;&#x5E55;&#x5FEB;&#x7167; 2019-04-07 &#x4E0B;&#x5348;5.29.47.png](https://cdn.nlark.com/yuque/0/2019/png/120638/1554629445773-3f1c30a9-2e5c-4c92-8bc0-03306d73ef4c.png#align=left&display=inline&height=272&name=屏幕快照%202019-04-07%20下午5.29.47.png&originHeight=1050&originWidth=848&size=275848&status=done&width=220)

单击“自定义字段”按钮，在弹出的对话框中可以添加或删除字段，如图所示。使用“自定义字段”功能可以根据需求定制“说明”界面。  
![&#x5C4F;&#x5E55;&#x5FEB;&#x7167; 2019-04-07 &#x4E0B;&#x5348;5.30.04.png](https://cdn.nlark.com/yuque/0/2019/png/120638/1554629464441-07c38c8c-4872-4baa-b9ce-cbb77043676b.png#align=left&display=inline&height=310&name=屏幕快照%202019-04-07%20下午5.30.04.png&originHeight=710&originWidth=872&size=184513&status=done&width=381) 

#### 1.3.2　对整个原型的“说明”

在原型的站点地图首页，可以为整个原型添加“说明”，如图所示。在这个页面中解释原型的主要内容，以及如何使用这个原型。另外，还可以在“说明”中提供制作者的联系方式，以方便与团队其他成员沟通。  
![&#x5C4F;&#x5E55;&#x5FEB;&#x7167; 2019-04-07 &#x4E0B;&#x5348;5.30.22.png](https://cdn.nlark.com/yuque/0/2019/png/120638/1554629508485-4f5a6bdc-0882-494d-a992-7596add387e6.png#align=left&display=inline&height=364&name=屏幕快照%202019-04-07%20下午5.30.22.png&originHeight=1396&originWidth=2148&size=1615334&status=done&width=560)

#### 1.3.3　结构图、流程图

在原型中，可以添加介绍原型整体的结构图、流程图，以便读者可以清楚地看到产品的整体设计思路，更容易理解产品结构和功能流程。

Axure RP中默认带有结构图、流程图的元件库为Flow元件库，如图所示。Flow元件库中包含了20多种常用的元件。  
![&#x5C4F;&#x5E55;&#x5FEB;&#x7167; 2019-04-07 &#x4E0B;&#x5348;5.34.14.png](https://cdn.nlark.com/yuque/0/2019/png/120638/1554629669558-cd911071-3cef-477c-adec-2d62f9a06bd6.png#align=left&display=inline&height=332&name=屏幕快照%202019-04-07%20下午5.34.14.png&originHeight=1066&originWidth=848&size=363613&status=done&width=264)

**（1）、流程图**  
如图所示为一个描述积分兑换流程的流程图。  
![&#x5C4F;&#x5E55;&#x5FEB;&#x7167; 2019-04-07 &#x4E0B;&#x5348;5.34.58.png](https://cdn.nlark.com/yuque/0/2019/png/120638/1554629707821-2c2ad5e1-b3ee-4f8b-93ec-996e4dcc2b87.png#align=left&display=inline&height=478&name=屏幕快照%202019-04-07%20下午5.34.58.png&originHeight=1208&originWidth=798&size=283036&status=done&width=316)

在流程图中，通常用不同的图形代表不同的含义。  
**·矩形：**代表流程中的“步骤”。  
**·菱形：**代表条件判断。  
**·椭圆形：**代表流程的起始和终止。

**（2）、结构图**  
结构图常用来表示产品的信息架构和页面逻辑。通常用不同的图形代表不同的含义。  
**·矩形：**代表各个页面。  
**·线：**连接各个页面，代表页面的访问路径。

如图所示为一个新闻平台的信息结构图。  
![&#x5C4F;&#x5E55;&#x5FEB;&#x7167; 2019-04-07 &#x4E0B;&#x5348;5.37.04.png](https://cdn.nlark.com/yuque/0/2019/png/120638/1554629832526-edf2387e-449c-42fd-831c-067342c49957.png#align=left&display=inline&height=376&name=屏幕快照%202019-04-07%20下午5.37.04.png&originHeight=1540&originWidth=2136&size=673800&status=done&width=521)

**提示：**  
（1）结构图上，页面名称最好与原型的站点地图中的页面名称对应。  
（2）可以在矩形元件上添加“动作”，通过单击各元件跳转至各页面，这样查看原型更方便。

### 1.4　结构规划

在制作原型前，最好先规划好原型的结构，为将来的修改预留空间。在制作过程中，应该随时调整结构，保持结构简单清晰，易于理解。

#### 1.4.1　原型结构——选择“页面”或“动态面板”

在动手制作原型之前就要考虑：原型的各个页面用“页面”，还是“动态面板”来做？  
![&#x5C4F;&#x5E55;&#x5FEB;&#x7167; 2019-04-07 &#x4E0B;&#x5348;5.47.10.png](https://cdn.nlark.com/yuque/0/2019/png/120638/1554630444008-1cb78d60-1a20-4feb-af58-c36139442f23.png#align=left&display=inline&height=254&name=屏幕快照%202019-04-07%20下午5.47.10.png&originHeight=1052&originWidth=2000&size=974786&status=done&width=482)

·如果页面比较多，而且制作的是网站原型，那么最好在站点地图中添加多个页面来实现原型，如图a所示。  
·如果页面切换的交互比较多、比较复杂，可以考虑用动态面板来实现原型，如图b所示。“动态面板”中的一个状态就是一个页面。状态间可以方便地传送数据。交互动画可以通过“设置面板状态”来实现。唯一的缺点是如页面较多，则预览原型时加载速度会比较慢。

#### 1.4.2　减少重复的动作和数据

**1.减少重复的动作**  
重复是可维护性的大敌。当意识到有相同的动作重复出现时，结构规划时应该尽量思考是否将这个动作抽出来，只写一次。

例如：

```text
·用例1，包括动作A和动作C。

·用例2，包括动作B和动作C。
```

用例1和用例2都包含了动作C。如果分别在两个用例中都有这个动作，修改时会比较麻烦。一旦只修改了一个，忘了修改另一个，就可能造成难以察觉的错误。

比较好的办法是：新建一个用例3。去掉用例1、2中的动作C，将动作C添加到用例3中。用例3的条件可以设为if true。让用例1和用例2执行之后都会执行用例3。这样，交互效果没变，但是以后动作C只需在一处修改即可，可维护性提高了。

**2.减少重复的数据**  
原型中，常有一些数据（如数字、文本、日期等格式）要在多处用到。这些数据一旦需要修改，就要挨个页面进行查找，很容易漏掉。

如果这个数据比较重要，可以在“页面加载时”事件中创建一个变量，用“设置变量值”动作将数据赋值给变量。需要用到数据时，不直接填写，而是使用变量。这样，当需要修改数据时，直接在一处修改即可，避免了漏改、忘改的情况。

#### 1.4.3　分割用例

原型中应该尽量将用例分割开。让每个用例只负责一个功能。一个用例内的动作不要过多。如果一个用例有超过20个动作，那么这个用例基本上是不可理解的。

分割用例的一个办法是将一些动作放在目标元件中。例如：  
（1）对动态面板的操作，可以将“动作”设置在动态面板的“状态改变时”事件中。  
如想对动态面板进行操作时，使用动作“设置面板状态”，该面板的“状态改变时”事件就会被触发，进而执行动作。

（2）对中继器的操作，可以将“动作”设置在中继器的“每项加载时”事件中。  
如果想对中继器进行操作时，只要使用动作“添加行”或“更新行”，中继器的“每项加载时”事件就会被触发，进而执行动作。

这样设置，不但避免了用例中动作过多，而且查找起来也更方便。

### 1.5　案例：Flappy Bird游戏案例

游戏中的交互动画通常比APP、网站的交互动画多。只要有合理的规划，Axure RP也可以制作出非常复杂的游戏原型。

以一款火遍全球的游戏Flappy Bird为例，展示如何规划、制作复杂的原型。

下载地址：[《flappybird.rp》](https://pan.baidu.com/s/14ikKkTiEKKvxonVC0U2pZA) 提取码: s5hm

## 二、原型设计准则

本章分别从制作原型的技巧、设计产品的思路和用户体验等几个方面介绍一些设计原型的经验。当然，所有规则都是可以打破的。读者可以参照本书，结合自身的经验，摸索出属于自己的原型设计规则。

### 2.1　原型做成高保真还是低保真

按精细程度，原型可以分为高保真原型或低保真原型。原型应该做成高保真还是低保真一直是个很有争议的问题。本节将解释两者的含义，并提出如何在两者间选择的建议。

#### 2.1.1　什么是高保真和低保真

原型按精细程度可以分为高保真原型与低保真原型两种，如图3-1所示。低保真原型通常只是简单的线框图示意。而高保真原型则看起来更像实际产品，可以点击，可以有各种交互，看起来与真实的网页、APP一样。  
![&#x5C4F;&#x5E55;&#x5FEB;&#x7167; 2019-04-07 &#x4E0B;&#x5348;5.54.34.png](https://cdn.nlark.com/yuque/0/2019/png/120638/1554630885377-bcaccfe0-6d96-4ab5-b8d6-a4e9bdaa1cf2.png#align=left&display=inline&height=281&name=屏幕快照%202019-04-07%20下午5.54.34.png&originHeight=1356&originWidth=2062&size=1447571&status=done&width=428)

#### 2.1.2　如何选择高保真与低保真

很多人在是否用Axure RP做高保真原型上犹豫不决、争论不休。  
（1）前台设计使用Axure RP制作低保真原型。

（2）有规范的视觉规范库，并且设计中后台产品功能用高保真原型，一般使用Sketch。

（3）Axure RP制作低保真原型，Sketch等制作高保真原型。 

### 2.2　原型中要使用真实的数据

原型中应该尽量使用真实数据，模拟真实情况。因为只有使用真实数据，才能分析出准确的需求。

例如图3-2中的原型，要试试真实的书的封面，才知道图片要放多大能看清楚；要试试真实的书名，才知道要预留多少空间，书名是否足够吸引，是否需要加书的简介……所有信息都是真实的，才能准确规划页面布局用卡片合适，还是列表合适。 

### 2.3　产品流程应该尽量完整

绘制原型要做出完整流程，尽可能考虑多种情况。设计原型时很容易想到正常的流程，但容易忽略分支流程和异常情况。

#### 2.3.1　考虑用户出错的情况

用户出错是难免的，所以应该允许细微的纠正，如更换账号、更换地址等。

#### 2.3.2　考虑系统出错的情况

例如，上传图片时，文件上传失败，或者对上传的图片不满意想换一张时，产品应该拥有重试和重做功能。

#### 2.3.3　考虑没有数据的情况

如果没有初始数据，用户看到的就是一片空白，此时用户可能不知道该干什么。可以利用好没有数据的初始界面，让用户学习和熟悉如何使用程序，引导用户创建数据。

#### 2.3.4　考虑每一步的状态

例如，电商订单有发货、收货状态，邮件有已读或未读的状态，支付有支付成功或未支付的状态。可以通过不同的视觉风格，如颜色、深度和对比度帮助用户清楚地知道目前的状态，以及接下来要干什么事。

#### 2.3.5　添加适当的提示

当用户执行了一个动作，应该有成功或失败的提示。例如，发布文章之后是否发送成功。发送邮件之后是否发送成功。修改的设置选项是否保存。

### 2.4　原型需要快速迭代

在软件开发中，“修改”是一件成本非常高的事。前期越能发现错误，修改成本就越低。在原型阶段发现错误，只要产品经理用几天时间改一下原型即可。如在研发结束之后才发现错误，则需要整个团队重新开始，或许要用几个月的时间才能做出正确的产品。因此为什么要先绘制原型，而不是直接研发产品呢？就是为了能尽早发现错误，尽早修改。

#### 2.4.1　沟通原型的技巧

在设计原型的过程中，需要不断地向身边的人请教意见，不断“试错”。切忌一个人纸面上画画就完成的原型制作，一定要找内部或外部的人来探讨。

（1）与别人沟通前应该准备一个有“沟通能力”的原型。原型做得简陋，就没有代入感。一般人很难对着线框提建议。使用真实的图片和文字，模拟完整的使用流程，做出有“沟通能力”的原型，对产品经理分析需求很有帮助。  
（2）与他人沟通时，不要维护自己的原型设计。只有不断地修改，才能打磨出有价值的产品原型。拿着原型初稿与他人沟通时，要有一种随时准备“推倒”重来的气魄。  
（3）尝试去理解对方的真正需求。在与他人沟通时，肯定会遇到不懂产品设计的人对你设计的原型指指点点。千万不要轻易陷入对方编织的理由中。将对方喜欢的方式设计出来，拿着修改后的设计继续向其他人请教，对比之后，更容易得出正确的结论。  
（4）时刻关注产品整体。修改过几次之后，可能已经改进了不少产品的细节。这时需要停一下，站在整个产品的角度重新审视一下——细节改进有没有打乱整体规划，量变是否已经引起质变，产品结构是否能更优化等。

#### 2.4.2　修改原型的技巧

即使是经验丰富的产品经理，也很少在第一次设计时就能达到满意的效果。大部分时候，都要经历5～10次的反复迭代。而且，有时迭代不只影响一页，甚至影响十几页或者更多。因此，只有提高绘制原型的效率才能应对频繁的更改。下面介绍一些提高Axure RP效率的方法。

（1）使用图形，而不是图片。在Axure RP中是无法改变一个图片的颜色和形状的。直接截图放进原型是一个看似快捷的办法。别忘了，原型一般都要修改多次，使用可以修改的图形元件而不是图片，可以更方便修改，更好地适应不同的需求。所以，别嫌麻烦，用图形元件一点一滴地搭建自己的原型吧。  
（2）用一个元件就可以完成的事不要用两个元件。每添加一个元件，都会给未来添加一份维护的工作。当原型需要改变时都要耗费更多的工作时间。例如，不要用文字和矩形两个元件来表示一个按钮，直接在矩形元件上输入文本。文本的位置可以通过对齐和填充属性来自由调整。给按钮添加交互事件时，不要添加热区再给热区设置交互，直接在按钮上设置交互即可，如图所示。  
![&#x5C4F;&#x5E55;&#x5FEB;&#x7167; 2019-04-07 &#x4E0B;&#x5348;6.25.48.png](https://cdn.nlark.com/yuque/0/2019/png/120638/1554632760102-3857abe6-327d-4515-b31e-ffc5d3817cd8.png#align=left&display=inline&height=78&name=屏幕快照%202019-04-07%20下午6.25.48.png&originHeight=224&originWidth=862&size=146735&status=done&width=301)

（3）将常用的一组元件转成母版。更改所有页面的导航栏的工作量非常大，而且容易出错。但是如果事先把导航栏做成母版，更改时只需编辑一个母版，那么整个原型就都被更新了。所以，无论何时，如果发现自己一直在复制粘贴同一组元件，请创建一个母版。  
（4）保留旧的页面。原型页面经过几次修改之后，可能又要找回原来的页面。所以，在做修改页面前，最好保留旧的页面，如图所示。创建一个名为“旧版本”的文件夹。复制一份要修改的页面，保存在“旧版本”文件夹中，以便需要时随时找到。  
![&#x5C4F;&#x5E55;&#x5FEB;&#x7167; 2019-04-07 &#x4E0B;&#x5348;6.27.21.png](https://cdn.nlark.com/yuque/0/2019/png/120638/1554632850921-25b07d12-d2c3-4e9d-b479-c3139a859603.png#align=left&display=inline&height=179&name=屏幕快照%202019-04-07%20下午6.27.21.png&originHeight=866&originWidth=2098&size=702030&status=done&width=433)

（5）保留、导入旧版本的原型文件。原型修改几次之后会形成一个稳定的版本，通常会保存为一个RP文件。几个版本之后，会积攒多个RP文件。如果想在新版本文件中使用旧版本的页面，可以使用“RP文件导入”功能。在菜单栏中单击“导入”按钮，然后选择想导入的页面。

**提示：**  
虽然从这一个RP文件到另一个RP文件复制、粘贴是可以的，但样式是不会跟着一起粘贴过去的。重复使用样式、母版的最好方法就是使用导入功能，如图所示。  
![&#x5C4F;&#x5E55;&#x5FEB;&#x7167; 2019-04-07 &#x4E0B;&#x5348;6.28.38.png](https://cdn.nlark.com/yuque/0/2019/png/120638/1554632926314-704f9288-9577-4dda-8f5f-06c631a5d538.png#align=left&display=inline&height=268&name=屏幕快照%202019-04-07%20下午6.28.38.png&originHeight=1038&originWidth=2098&size=729780&status=done&width=542)

### 3.5　页面应该尽量简化

在功能层面，改进原型的主要方法是简化产品的使用流程。什么叫好的用户体验呢？从打开APP开始，用户一步一步下意识地被产品引导着完成功能流程。整个过程行云流水，用户使用完全没有障碍，完全沉浸在产品之中，这就是好的用户体验。如果用户使用过程中受到阻碍，用户体验就会差，则用户流失率就会提高。简化流程就是要简化掉这些阻碍，让用户使用起来畅通无阻。

#### 3.5.1　精简用户输入内容

人都是有惰性的，没人愿意填一大堆表单。表单中每增加一个字段，都会增加用户流失率，因此，表单页面尽量只留必填项，其他项放在“高级”页面里。必填项尽量以选择为主，填写为辅。必须填写的也应该尽量给出默认值。因为选择只需要一次单击，而填写则需要数次键盘操作。精简的目的就是使用更少操作完成同样的功能。

#### 3.5.2　精简页面上的元素

要让设计具有层次感，可以将界面上重要的部分与不次要部分区分开，让界面层次分明。但要注意过多的页面元素会分散用户的注意力。

#### 3.5.3　合并重复的功能

随着产品的发展，不可避免会增加很多的功能模块。应该及时重构产品，合并功能，避免产品“臃肿”，阻碍用户学习、使用。

页面很长或者分页的情况下，可以重复出现同一个按钮，但一定要慎用。例如，购物车中，如果列表过长则可以出现两次结算按钮。列表较短则没有必要，如图所示。

#### 3.5.4　避免过多的分支流程

为了满足各类用户的需求，增加功能是不可避免的。但有时是更多的选择往往让人更难做出决策，让后悔和自责倾向增加，甚至降低了用户满意度。著名的果酱研究实验一次次的被验证，当选项过多时，给出重点推荐项是个不错的做法。

例如雅虎新闻原型，不像其他的新闻APP一样有过多的分类、过多的选择，而是每半天提供8类8条最重要的新闻。

**小知识：**  
果酱实验的过程是这样的：  
第一次，在超市中卖果酱的货架上放置了24种果酱。顾客看到琳琅满目的商品纷纷驻足（60%），有的人还停下来参与试吃。但最后购买率只有3%。  
第二次，货架上只放置了6种果酱。在此停留的顾客有所减少（40%），但购买率却高达31%，是前一次实验的10倍。  
为什么是这样的结果呢？可能人们都有选择恐惧症。当人们有太多的选项时，很容易最后什么都不选。而选项简单，决策就容易，顾客就有更大的概率购买。

#### 3.5.5　减少确认环节

确认操作的目的是为了避免误操作。过多的确认操作反而影响用户的正常操作流程。因此，应当尽量减少确认操作，只在必要时弹出确定窗口。一般情况下，可以考虑使用不影响用户的撤销提示。

例如，删除邮件时，会弹出撤销窗口。如果用户是误操作，那么可以点“撤销”按钮恢复删除的邮件。如果用户没有误操作，那么可以继续进行其他操作，页面底部提示气泡会自然消失。

### 3.6　页面布局要随时优化

在结构层面，改进原型的方法是优化布局。怎样布局算是优化好了呢？

有一个简单的测试方法。打开原型，看两秒钟，然后关掉，立即回忆。  
·如果第一个回忆起来的是页面最想表达的东西，那么这个页面就算布局好了。  
·如果第一个回忆起来的只是页面上优先级比较低的内容，那就说明页面的层次关系有问题，页面的重点不对。

真正重要的东西应该更突出，次要的东西应该弱化。

这个方法可以自测，也可以请他人帮忙测试。但是一个人只能测一遍，第二遍就会有先前的印象影响判断，所以第二遍测试一定要换人。

#### 3.6.1　用图形替代文字

图形比文字更易懂，应该用直观的图形展示替代直白的文字描述。

文字部分应该尽量简洁明了。文字过多会增加用户的阅读成本和理解成本。如果文字内容确实比较多，应该摘要显示，用户感兴趣再查看更多，而不是直接全部展开。

#### 3.6.2　突出重点信息

类似的多个信息应该显示出最相关的几个属性差异。对比信息时，用表格形式比较清晰明确。

例如，图中就是一个价格体系的介绍页面。应用表格形式，有助于用户对比、决策。  
![&#x5C4F;&#x5E55;&#x5FEB;&#x7167; 2019-04-07 &#x4E0B;&#x5348;6.37.30.png](https://cdn.nlark.com/yuque/0/2019/png/120638/1554633477755-feead98a-7193-4ba2-8c72-9e6f0d6d694c.png#align=left&display=inline&height=249&name=屏幕快照%202019-04-07%20下午6.37.30.png&originHeight=1028&originWidth=2090&size=484028&status=done&width=506)

#### 3.6.3　把握页面节奏

把页面做得环环相扣，要好过平铺直叙。没有节奏的页面会让用户失去兴趣，无所适从，进而造成顾客流失。

应该在页面中适当地设置一些小节，注意图文的比重、各模块的分隔、页面样式的统一。页面应节奏紧凑，环环相扣。

### 3.7　要保持原型的一致性

原型的一致性分为外部一致性和内部一致性。外部一致性要求尽量与其他产品保持一致，降低用户的学习成本。内部一致性要求产品中所有页面保持一致，降低用户的使用成本。

#### 3.7.1　遵从惯例，保持外部一致

遵从惯例，使用用户已经熟悉的交互流程与页面样式，会降低用户学习成本，用户用起来会很方便。相反，与外部不一致则会提高学习成本。例如，用户想都不用想就知道界面右上角的叉叉是关闭页面用的。点击一个按钮后，用户知道会发生一些变化。

当然，惯例是会过时的，随着时间的推移，同样的操作可能被赋予新的含义。但是，打破常规时一定要注意，对于设计者显而易见的东西可能对用户不是这样的。  
![&#x5C4F;&#x5E55;&#x5FEB;&#x7167; 2019-04-07 &#x4E0B;&#x5348;6.40.26.png](https://cdn.nlark.com/yuque/0/2019/png/120638/1554633636014-a2c870d0-8ca1-4851-955a-a618ea230f2e.png#align=left&display=inline&height=609&name=屏幕快照%202019-04-07%20下午6.40.26.png&originHeight=1570&originWidth=1028&size=923635&status=done&width=399)

#### 3.7.2　统一样式，保持内部一致

一个产品内的各个页面的样式应该尽量保持一致，以减少用户的学习成本。用户不需要学习新的操作。例如，各个页面的颜色，按钮的大小样式，点击、拖曳的操作效果等各方面都应该保持一致。

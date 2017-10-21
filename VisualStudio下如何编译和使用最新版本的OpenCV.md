# VisualStudio下如何编译和使用最新版本的OpenCV

[![在Windows上安装OpenCV 3](http://www.learnopencv.com/wp-content/uploads/2017/05/install-opencv-3-on-windows.jpg)](http://www.learnopencv.com/wp-content/uploads/2017/05/install-opencv-3-on-windows.jpg)

在这篇文章中，我们将提供一些关于如何在Windows上安装OpenCV 3（C ++和Python）的说明。

## 步骤1：安装Visual Studio

从<https://www.visualstudio.com/vs/older-downloads/>下载并安装Visual Studio 2015社区版本。您也可以使用Visual Studio 2017，但如果您打算使用Dlib，则必须使用Visual Studio 2015，因为Dlib无法使用Visual Studio 2017进行编译

运行安装程序，在“安装类型”中选择“自定义”。

[![安装Visual Studio 2015](http://www.learnopencv.com/wp-content/uploads/2017/05/install_visual_studio_2015-1-300x300.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/install_visual_studio_2015-1.png)

在编程语言的下一个屏幕中，选择Visual Studio的Visual C ++和Python工具。点击下一步。
[![安装Visual Studio 2015](http://www.learnopencv.com/wp-content/uploads/2017/05/install_visual_studio_2015-2-300x300.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/install_visual_studio_2015-2.png)

现在点击下一步。完成安装需要一些时间。

[![安装Visual Studio 2015](http://www.learnopencv.com/wp-content/uploads/2017/05/install_visual_studio_2015-4-300x300.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/install_visual_studio_2015-4.png)

我们已经完成了Visual Studio 2015的安装。

 

## 步骤2：安装CMake

从<https://cmake.org/download/>下载并安装CMake v3.8.2 。

[![下载CMake v3.8](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0004-1024x576.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0004.png)

在安装过程中，选择“将CMake添加到系统路径”

[![将CMake添加到系统PATH](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0007-1024x577.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0007.png)

## 步骤3：安装Anaconda（一个python发行版）

Anaconda是一个Python发行版，它附带了许多有用的Python包。有时在Windows上安装Python模块可能会造成巨大的痛苦。为Python生成OpenCV二进制文件不需要安装Anaconda。你也可以使用官方的Python和NumPy。

从<https://www.continuum.io/downloads>下载并安装Anaconda 64位版本。您可以安装Anaconda 2或Anaconda 3或两者。

[![下载并安装64位Anaconda 2或Anaconda 3或两者兼容](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0010-1024x576.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0010.png)

安装Anaconda时，请确保您同时检查这两个选项：

1. 将Anaconda添加到我的PATH环境变量中
2. 将Anaconda注册为我的默认Python

[![将Anaconda添加到系统PATH并将其设为默认Python](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0016-1024x576.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0016.png)

## 步骤4：下载opencv和opencv_contrib

转到<https://github.com/opencv/opencv/releases>并下载opencv-3.2.0源代码zip

[![下载OpenCV 3.2.0](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0019-1024x576.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0019.png)

转到<https://github.com/opencv/opencv_contrib/releases>并下载opencv_contrib-3.2.0源代码zip

[![下载OpenCV contrib 3.2.0](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0020-1024x576.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0020.png)

提取两个zip文件。虽然您可以在任何地方保持opencv和opencv_contrib文件夹，但我建议您将这两个文件保存在同一目录中。我将这两个文件夹放在“我的文档”目录中。

从这里我们将把opencv-3.2.0文件夹的路径称为**OPENCV_PATH**。在我的情况下OPENCV_PATH是C：/ Users / Vaibhaw Chandel / Documents / opencv-3.2.0

根据你在哪里保存opencv-3.2.0文件夹，这个路径会有所不同。

[![将OpenCV 3.2.0和OpenCV contrib 3.2.0提取到同一文件夹](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0022-1024x575.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0022.png)

## 步骤5：使用CMake生成Visual Studio项目

#### 步骤5.1：配置默认标志

运行Cmake GUI。在“哪里的源代码”框中写入**OPENCV_PATH的**值（这是opencv-3.2.0文件夹的路径）和路径构建目录。我们将选择构建目录为OPENCV_PATH / build。点击配置。

[![在CMake GUI中为OpenCV源和路径创建目录，然后单击“配置”](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0028-1024x555.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0028.png)
它将要求您创建构建文件夹的权限。只需点击是。它还会要求您选择一个编译器。由于我们使用Visual Studio 2015，我们将选择Visual Studio 14 2015 Win64。

[![选择Visual Studio 2015 64位作为生成器](http://www.learnopencv.com/wp-content/uploads/2017/05/select-visual-studio-2015-64-bit-as-generator-1024x879.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/select-visual-studio-2015-64-bit-as-generator.png)

单击完成，并在下一个窗口中保留默认参数。点击完成。现在，CMake将查看系统目录并生成makefile。[![选择Visual Studio 2015作为生成器和默认编译器](http://www.learnopencv.com/wp-content/uploads/2017/05/select-visual-studio-default-compiler-1024x897.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/select-visual-studio-default-compiler.png)

 

#### 步骤5.2：配置其他CMake标志

我们将对CMake生成的默认配置进行几个更改。

1. 检查“INSTALL_C_EXAMPLES”和“INSTALL_PYTHON_EXAMPLES”
2. 在标志“OPENCV_EXTRA_MODULES_PATH”中，给出opencv_contrib-3.2.0中modules目录的路径。在我们的例子中，我们在Documents文件夹中保留了opencv_contrib-3.2.0，所以路径是“C：/ Users / Vaibhaw Chandel / Documents / opencv_contrib-3.2.0 / modules”

[![在CMake GUI中检查C示例和Python示例，以便它们与OpenCV库一起构建](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0037-1024x555.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0037.png)

[![指定opencv_contrib / modules目录的路径](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0040-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0040.png)
现在再次点击配置。

#### 步骤5.3：配置Python标志

此部分仅适用于要为Python2和Python3生成OpenCV二进制文件的人员。如果要使用2或3中的一个Python，则应跳过此部分。
CMake找到Python2的路径，但无法找到我的Python3文件的路径。

[![为OpenCV构建文件配置Python标志](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0049-1024x544.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0049.png)

所以我手动添加了Python3的路径。

[![在CMake中添加了Python 3路径](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0055-1024x555.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0055.png)

现在再次单击配置。配置完成后，在搜索栏中搜索opencv_python，将自动检查BUILD_opencv_python2和BUILD_opencv_python3。现在我们确定在编译后将生成Python2和Python 3的OpenCV二进制文件。

[![检查将生成哪个Python（2或3或两者）构建](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0064-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0064.png)

#### 步骤5.4：生成CMake文件

如果CMake能够配置没有任何错误，它应该说“配置完成”。点击生成。
这是非常重要的一点。每当您对CMake生成的配置进行任何更改（检查/取消选中框或更改路径）时，请始终单击configure并生成。

## 步骤6：编译OpenCV

#### 步骤6.1：在Visual Studio中打开项目

一旦CMake生成了必要的文件，点击Open Project。如果要求使用哪个应用程序来打开项目，请选择Visual Studio 2017。

[![在Visual Studio中打开项目](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0070-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0070.png)

[![选择Visual Studio 17作为应用程序打开由CMake生成的OpenCV构建项目](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0073-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0073.png)

OR而不是单击“打开项目”，您可以转到您的构建文件夹，即OPENCV_PATH /构建，并双击.sln文件。这将打开Visual Studio。
在Visual Studio中，您可以在不同的配置设置中构建一个项目。我们将构建具有两种配置的OpenCV：

1. 调试模式 - x64平台
2. 发布模式 - x64平台。

**要特别注意这一点。当您在Visual Studio中构建解决方案时，请确保该模式为Debug或Release，而platform为x64。**

#### 步骤6.2：配置x64或释放模式

如果x64作为平台选项不存在，请单击调试，然后在下拉菜单中选择配置管理器。
[![检查该模式应该是Debug，并且平台为x64](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0079-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0079.png)

 

现在点击x86，然后从下拉菜单中选择新建。在出现的新窗口中，选择x64为“新平台”，并在“复制设置”中保留x86。单击确定。

[![在Visual Studio 17的配置管理器中创建x64平台](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0082-1024x539.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0082.png)

[![将设置从x86复制到创建x64平台类型](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0083-1024x550.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0083.png)
同样，如果发布模式不存在，请单击配置管理器 - >调试 - >新建。在“名称”中键入释放并在“复制设置从”中调试。现在我们完成了在Visual Studio中创建构建配置。

[![通过从调试模式复制设置来创建发布模式](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0084-1024x551.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0084.png)

#### 步骤6.3：在调试模式下构建OpenCV

选择模式作为调试，并从下拉菜单中定位为x64。在解决方案资源管理器（位于左侧的面板）下，在CMakeTargets下查找INSTALL，右键单击选择构建。

[![现在在Debug x64中构建OpenCV](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0088-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0088.png)

它可能给生成Python二进制错误。你可以忽略它，因为我们将使用从发布模式生成的Python二进制文件。

#### 步骤6.4：在释放模式下构建OpenCV

选择模式作为释放，并定位为x64。再次右键单击CMakeTargets下的“INSTALL”，然后选择Build。一旦生成完成，请检查日志。它应该看起来像这样：

[![在版本x64模式和最终构建日志中构建OpenCV](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0094-1024x558.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0094.png)

现在我们已经编译了OpenCV，我们将了解如何配置Visual Studio项目以使用OpenCV库。

## 步骤7：测试C ++代码

从[这里](http://www.learnopencv.com/wp-content/uploads/2017/03/RedEyeRemover.zip)下载C ++和Python代码 并将其提取到文件夹中。

#### 步骤7.1：更新系统环境变量

首先我们将添加OpenCV dll文件的路径到我们的系统PATH。按Windows超级键，搜索“环境变量”。

[![从Windows搜索菜单中搜索系统环境变量](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0181-1024x555.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0181.png)

单击系统属性窗口中的环境变量。

[![编辑环境变量](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0184-1024x555.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0184.png)

在系统变量下，选择路径并单击编辑。

[![编辑系统环境变量 - 路径](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0187-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0187.png)

单击新建，并给OPENCV_PATH \ build \ install \ x64 \ vc15 \ bin的路径，然后单击确定。根据您在哪里保存opencv-3.2.0文件夹以及您用于编译OpenCV的Visual Studio版本，此路径将不同。在我的情况下，完整的路径是：
C：\ Users \ Vaibhaw Chandel \ Documents \ opencv-3.2.0 \ build \ install \ x64 \ vc15 \ bin

[![在PATH变量中追加生成OpenCV二进制文件夹的路径 ](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0196-1024x555.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0196.png)

 

#### 步骤7.2：创建新项目

现在我们将在Visual Studio中创建一个新项目。

[![在Visual Studio 17中创建新项目](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0097-1024x558.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0097.png)

 

在下一个窗口中，在“模板”中选择Visual C ++然后“Win32控制台应用程序”，给出项目名称和解决方案名称，然后单击确定。我在项目名称和解决方案名称中给了“RedEyeRemover”。

[![Speficy项目名称和解决方案名称和模板作为Win32控制台应用程序](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0106-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0106.png)
在下一个窗口中，选择控制台应用程序，并选中“空项目”，单击完成。

[![选择应用程序类型作为控制台应用程序创建空项目](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0109-1024x555.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0109.png)
现在我们将添加一个新的文件与源文件。右键单击源文件，单击新建项。

[![在源目录中创建新的C ++文件](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0112-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0112.png)

在下一个窗口中，选择C ++文件并给该文件命名。我给了redEyeRemover.cpp的名字

[![将文件指定为C ++并提供文件名](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0115-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0115.png)
这将创建一个空的C ++文件。我们已经下载并提取了RedEyeRemover的代码。将代码从removeRedEyes.cpp复制到此文件。

#### 步骤7.3：指定OpenCV包含目录路径

**注意：**在继续之前，请确保下拉菜单中的配置为Debug和x64，因为当我们创建一个新项目时，默认情况下可能会在Debug和x86中打开。

可以看到Visual Studio显示了很多错误（定义未找到错误）。这是因为Visual Studio不知道OpenCV的头文件的存放位置。我们需要添加OpenCV头文件的路径，以便我们可以编译OpenCV库文件的项目和路径，以便链接器可以访问库文件。右键单击您的项目并选择属性。

[![打开Visual Studio项目的属性](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0118-1024x555.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0118.png)
注意：在继续之前，请确保“配置属性窗口”下拉菜单中的配置是Debug和x64。

在“配置属性” - > C / C ++ - >常规下，单击“其他包含目录”。

[![在C / C ++选项的常规下编辑“其他包括目录”框](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0121-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0121.png)

您可以通过点击红色图标左侧的文件夹图标添加路径。您必须在此添加3个路径：

在我的情况下，路径是：

[![指定OpenCV包含目录路径](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0127-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0127.png)

单击确定。

[![保存设置](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0133-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0133.png)

现在你会看到，定义没有发现错误在Visual Studio中消失。

[![我们的C ++项目中现在没有找到定义错误](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0136-1024x555.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0136.png)

 

#### 步骤7.4：指定OpenCV库路径

现在我们将添加库目录的路径。单击左侧面板中的链接器，然后单击其他库目录。

[![在“链接器”选项下编辑“附加库目录”](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0139-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0139.png)

您必须在这里添加路径**OPENCV_PATH** \ build \ install \ x64 \ vc15 \ lib。

[![指定OpenCV库路径](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0142-1024x555.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0142.png)

 

#### 步骤7.5：指定OpenCV库

在链接器中点击输入。在这里我们将提到我们将要使用哪些库文件。现在在“附加依赖关系”字段中，我们将添加所有OpenCV库文件的名称。

[![在“链接器中的输入”选项下编辑“附加依赖关系”框](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0145-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0145.png)
我们在Debug模式和Release模式下编译了OpenCV。所以每个库文件有2个版本。

[![OpenCV调试和发布库是不同的](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0148-1024x555.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0148.png)

在这里的屏幕截图中，您可以看到前两个文件名为
opencv_aruco320.lib和opencv_aruco320d.lib。第一个文件是在Release模式下创建的，而在Debug模式下创建。**d**在第二个文件中表示调试。
这里要注意的一点是，如果您选择“配置”为“调试”，则应在“附加依赖关系”中添加调试库文件，如果选择“配置”为“释放”，则应在此添加发布库文件。 我创建了所有OpenCV库文件的列表，将其复制并添加到“附加依赖关系”框中。**320**代表版本**3.2.0**。

[![指定所有OpenCV库](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0154-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0154.png)

另一重点：由于我们为x64平台构建了OpenCV，因此我们将始终在项目中使用平台“x64”。

#### 步骤7.6：复制项目文件

现在右键单击项目（RedEyeRemover），单击“在文件资源管理器中打开文件夹”。从我们下载并提取的redEyeRemover项目中将文件red_eyes.jpg，red_eyes2.jpg和haarcascade_eye.xml复制到此文件夹。所有这些文件应该在redEyeRemover.cpp文件旁边。

[![所有项目文件都保存在同一个文件夹中](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0160-1024x553.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0160.png)

#### 步骤7.7：构建redEyeRemover项目

我们现在全部要建立我们的应用程序。再次确保在Visual Studio中Debug和platform是x64的模式。单击调试，选择“启动不调试”。

[![通过选择“开始不调试”构建项目](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0166-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0166.png)

当它要求构建项目时选择“是”。

[![单击是构建项目](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0169-1024x557.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0169.png)

如果应用程序正确构建，您将看到两个图像显示窗口。一个有红眼，另一个没有红眼。

[![将出现2个显示窗口，一个带有红眼睛的另一个黑眼睛](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0205-1024x557.jpg)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0205.jpg)

### 步骤8：测试Python代码

#### 步骤8.1：快速检查

检查OpenCV for Python的快速方法是否正确安装是在python解释器中导入cv2。在Windows中打开命令提示符，运行python命令。这将打开Python解释器。运行这两个命令

注意：它是cv2 .__ version__。下划线在上面的代码段中不可见。

Anaconda配备了一个功能丰富的Python解释器，称为IPython。我在IPython中测试了这些命令。

[![OpenCV导入Python并检查OpenCV的版本](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0238-1024x581.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0238.png)

如果OpenCV for Python安装正确，运行命令“import cv2”将不会出错。如果出现任何错误，意味着安装失败。

#### 步骤8.2：运行redEyeRemover python脚本

打开Windows命令提示符，转到保存Python文件（removeRedEyes.py）并运行的文件夹

我在Windows Power Shell中做了同样的工作。您可以在命令提示符或Power Shell中执行此操作。

[![从命令提示符运行Python脚本](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0251-1024x322.png)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0251.png)

如果程序成功运行，您将看到两个图像窗口，一个具有红眼，另一个用黑眼睛。

[![将出现2个图像窗口，一个带有红眼睛，另一个用黑眼睛](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0253-1024x556.jpg)](http://www.learnopencv.com/wp-content/uploads/2017/05/opencv_0253.jpg)
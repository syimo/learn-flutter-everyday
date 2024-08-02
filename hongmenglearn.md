> 基于现有的flutter项目，打包成鸿蒙next安装包的记录
  
#### 1.配置环境
- 下载适配过鸿蒙的flutter_flutter版本，[点击下载](https://gitee.com/openharmony-sig/flutter_flutter)
- 第二步，下载鸿蒙开发套件，内置了开发需要的组件，[点击下载](https://developer.huawei.com/consumer/cn/download/deveco-studio)

#配置flutter sdk  
export PATH=<flutter_flutter path>/bin:$PATH  
export PUB_HOSTED_URL=https://pub.flutter-io.cn
export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn  

#配置dev studio  
export TOOL_HOME=/Applications/DevEco-Studio-5.0.3.300.app/Contents # mac环境
export DEVECO_SDK_HOME=$TOOL_HOME/sdk # command-line-tools/sdk
export PATH=$TOOL_HOME/tools/ohpm/bin:$PATH # command-line-tools/ohpm/bin
export PATH=$TOOL_HOME/tools/hvigor/bin:$PATH # command-line-tools/hvigor/bin
export PATH=$TOOL_HOME/tools/node/bin:$PATH # command-line-tools/tool/node/bin


#### 2.项目打包

- 在当前flutter项目下生成ohs项目  
- 替换涉及到原生部分的插件[点击查看](https://gitee.com/openharmony-sig/flutter_packages)和[Flutter三方库适配计划](https://docs.qq.com/sheet/DVVJDWWt1V09zUFN2)
- 打包hap，具体如下：


  flutter create --platforms ohos .  
  flutter build hap --release

  dependencies:
    path_provider:
      git:
        url: "https://gitee.com/openharmony-sig/flutter_packages.git"
        path: "packages/path_provider/path_provider"


---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 753c92cdf2124ee7fb1b471c7bc543b6db6f3daa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653580"
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
显示使用 UTF-8 编码的编译器输出。  
  
## <a name="syntax"></a>语法  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>自变量  
 `+` &#124; `-`  
 可选。 此选项的默认值是`-utf8output-`，这意味着编译器输出不使用 utf-8 编码。 指定`-utf8output`等同于指定`-utf8output+`。  
  
## <a name="remarks"></a>备注  
 某些国际配置中，在编译器输出不能在控制台中正确显示。 在这种情况下，使用`-utf8output`和编译器输出重定向到一个文件。  
  
> [!NOTE]
>  `-utf8output`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译`In.vb`和指示编译器显示输出使用 utf-8 编码。  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

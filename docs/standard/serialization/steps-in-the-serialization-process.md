---
title: 序列化过程中的步骤
ms.date: 08/07/2017
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
ms.openlocfilehash: b44b3b0539237c0f0d0a4af877e8955c6f612003
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581815"
---
# <a name="steps-in-the-serialization-process"></a>序列化过程中的步骤
对[格式化程序](xref:System.Runtime.Serialization.Formatter)调用 <xref:System.Runtime.Serialization.Formatter.Serialize*> 方法时，将按照以下规则顺序进行对象序列化：

- 进行检查以确定格式化程序是否具有代理项选择器。 如果有，则检查代理项选择器是否处理给定类型的对象。 如果选择器处理该对象类型，则在代理项选择器上调用 <xref:System.Runtime.Serialization.ISerializable.GetObjectData*?displayProperty=nameWithType>。

- 如果没有代理项选择器，或者代理项选择器不处理该对象类型，则进行检查以确定是否用 [Serializable](xref:System.SerializableAttribute) 属性标记了该对象。 如果未标记该对象，则会引发 <xref:System.Runtime.Serialization.SerializationException>。

- 如果已相应地标记了对象，则检查该对象是否实现 <xref:System.Runtime.Serialization.ISerializable> 接口。 如果对象实现接口，则对该对象调用 <xref:System.Runtime.Serialization.ISerializable.GetObjectData*>。
  
- 如果对象未实现 <xref:System.Runtime.Serialization.ISerializable>，则使用默认序列化策略，从而序列化所有未标记为 [NonSerialized](xref:System.NonSerializedAttribute) 的字段。

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a>请参阅  
 [二进制序列化](binary-serialization.md)  
 [XML 和 SOAP 序列化](xml-and-soap-serialization.md)
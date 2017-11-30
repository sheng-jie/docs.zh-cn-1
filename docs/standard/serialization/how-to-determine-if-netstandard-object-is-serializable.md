---
title: "如何： 确定是否可序列化的标准.NET 对象"
description: "演示如何确定在运行时是否可以序列化.NET 标准的类型。"
ms.custom: 
ms.date: 10/20/2017
ms.prod: .net
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0460fe27228fb9e17bde2d10652164707cd47a8b
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2017
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="8a5e0-103">如何： 确定是否可序列化的标准.NET 对象</span><span class="sxs-lookup"><span data-stu-id="8a5e0-103">How to: Determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="8a5e0-104">.NET 标准是标准的定义的类型和特定于该版本符合的.NET 实现必须存在的成员的规范。</span><span class="sxs-lookup"><span data-stu-id="8a5e0-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="8a5e0-105">但是，.NET 标准未定义是否可序列化类型。</span><span class="sxs-lookup"><span data-stu-id="8a5e0-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="8a5e0-106">在.NET 标准库中定义的类型不会标记有<xref:System.SerializableAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="8a5e0-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="8a5e0-107">相反，特定的.NET 实现，如.NET Framework 和.NET 核心是可用来确定特定类型是否为可序列化。</span><span class="sxs-lookup"><span data-stu-id="8a5e0-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span> 

<span data-ttu-id="8a5e0-108">如果你面向的.NET 标准开发了一个库，你的库可供任何支持.NET 标准的.NET 实现。</span><span class="sxs-lookup"><span data-stu-id="8a5e0-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="8a5e0-109">这意味着，您无法事先知道特定类型是否是可序列化;你可以仅确定它是否是可序列化在运行时。</span><span class="sxs-lookup"><span data-stu-id="8a5e0-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="8a5e0-110">你可以确定对象是否可序列化在运行时检索的值的<xref:System.Type.IsSerializable>属性<xref:System.Type>对象，表示该对象的类型。</span><span class="sxs-lookup"><span data-stu-id="8a5e0-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="8a5e0-111">下面的示例提供一个实现。</span><span class="sxs-lookup"><span data-stu-id="8a5e0-111">The following example provides one implementation.</span></span> <span data-ttu-id="8a5e0-112">它定义`IsSerializable(Object)`扩展方法，该值指示是否有任何<xref:System.Object>可以序列化实例。</span><span class="sxs-lookup"><span data-stu-id="8a5e0-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="8a5e0-113">然后可以将任何对象传递给该方法以确定是否可序列化和它上当前的.NET 实现中，将如以下示例所示的反序列化：</span><span class="sxs-lookup"><span data-stu-id="8a5e0-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

# <a name="see-also"></a><span data-ttu-id="8a5e0-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a5e0-114">See also</span></span>

<span data-ttu-id="8a5e0-115">[二进制序列化](binary-serialization.md) </span><span class="sxs-lookup"><span data-stu-id="8a5e0-115">[Binary serialization](binary-serialization.md) </span></span>  
<span data-ttu-id="8a5e0-116"><xref:System.SerializableAttribute?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8a5e0-116"><xref:System.SerializableAttribute?displayProperty=fullName></span></span>    
<xref:System.Type.IsSerializable?displayProperty=nameWithType>   
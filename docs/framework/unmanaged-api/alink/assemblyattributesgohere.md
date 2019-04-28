---
title: AssemblyAttributesGoHere クラス (System.Runtime.CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHere
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHere
helpviewer_keywords:
- AssemblyAttributesGoHere type
- Alink API, AssemblyAttributesGoHere type
ms.assetid: 7b26fcb6-94f4-4f09-933e-b33efe451f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 571c2f6723e827a1b385f77724c33703ae970ae3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775623"
---
# <a name="assemblyattributesgohere-class"></a><span data-ttu-id="2fef9-102">AssemblyAttributesGoHere クラス</span><span class="sxs-lookup"><span data-stu-id="2fef9-102">AssemblyAttributesGoHere Class</span></span>

<span data-ttu-id="2fef9-103">ALink でプレースホルダーとして使用し、カスタム属性に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="2fef9-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="2fef9-104">構文</span><span class="sxs-lookup"><span data-stu-id="2fef9-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHere
```

## <a name="remarks"></a><span data-ttu-id="2fef9-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="2fef9-105">Remarks</span></span>

<span data-ttu-id="2fef9-106">この型への参照は、ソースにアセンブリのカスタム属性が含まれている netmodule 内部に埋め込まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="2fef9-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="2fef9-107">これらの型への参照が含まれる 1 つまたは複数の  netmodule からアセンブリ マニフェストを作成すると、ALink はこれらの参照にアタッチされた情報を使用して、実際のカスタム属性を生成します。</span><span class="sxs-lookup"><span data-stu-id="2fef9-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="2fef9-108">このため、この型がインスタンス化されることはなく、その型への参照はビルド処理の一部としてのみ使用され、最終的なアセンブリでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="2fef9-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="2fef9-109">この型への参照は、セキュリティに関連せず複数の用途を持たないカスタム属性を示します。</span><span class="sxs-lookup"><span data-stu-id="2fef9-109">References to this type indicate custom attributes that are not security related and are not multiple-use.</span></span>

<span data-ttu-id="2fef9-110">これらの型が「内部」.NET Framework 内でマークされ、内にある、<xref:System.Runtime.CompilerServices>名前空間。</span><span class="sxs-lookup"><span data-stu-id="2fef9-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="2fef9-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="2fef9-111">Requirements</span></span>

<span data-ttu-id="2fef9-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="2fef9-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="2fef9-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fef9-113">See also</span></span>

- [<span data-ttu-id="2fef9-114">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="2fef9-114">AssemblyAttributesGoHereM</span></span>](assemblyattributesgoherem.md)
- [<span data-ttu-id="2fef9-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="2fef9-115">AssemblyAttributesGoHereS</span></span>](assemblyattributesgoheres.md)
- [<span data-ttu-id="2fef9-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="2fef9-116">AssemblyAttributesGoHereSM</span></span>](assemblyattributesgoheresm.md)

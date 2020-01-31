---
title: IXCLRDataMethodDefinition インターフェイス
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 708c681a98113a406249a360c2fc81087e5b97f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790419"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="65a0e-102">IXCLRDataMethodDefinition インターフェイス</span><span class="sxs-lookup"><span data-stu-id="65a0e-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="65a0e-103">メソッド定義に関する情報を照会するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="65a0e-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="65a0e-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="65a0e-104">Methods</span></span>

<span data-ttu-id="65a0e-105">次のメソッドは、インターフェイスで使用できるメソッドの一部です。</span><span class="sxs-lookup"><span data-stu-id="65a0e-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="65a0e-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="65a0e-106">Method</span></span>                                                                                                                          | <span data-ttu-id="65a0e-107">説明</span><span class="sxs-lookup"><span data-stu-id="65a0e-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="65a0e-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="65a0e-108">StartEnumInstances</span></span>](ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="65a0e-109">指定された `IXCLRDataAppDomain`のメソッドインスタンスの列挙体のハンドルを提供します。</span><span class="sxs-lookup"><span data-stu-id="65a0e-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="65a0e-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="65a0e-110">EnumInstance</span></span>](ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="65a0e-111">このメソッド定義のインスタンスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="65a0e-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="65a0e-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="65a0e-112">EndEnumInstances</span></span>](ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="65a0e-113">インスタンスの列挙中に使用される内部反復子によって使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="65a0e-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="65a0e-114">コメント</span><span class="sxs-lookup"><span data-stu-id="65a0e-114">Remarks</span></span>

<span data-ttu-id="65a0e-115">このインターフェイスはランタイム内に存在し、ヘッダーまたはライブラリファイルを介して公開されることはありません。</span><span class="sxs-lookup"><span data-stu-id="65a0e-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="65a0e-116">ただし、これは、通常の COM 機構を通じて取得できる GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` を `IUnknown` から派生する COM インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="65a0e-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="65a0e-117">要件</span><span class="sxs-lookup"><span data-stu-id="65a0e-117">Requirements</span></span>

<span data-ttu-id="65a0e-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65a0e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="65a0e-119">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="65a0e-119">**Header:** None</span></span>  
<span data-ttu-id="65a0e-120">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="65a0e-120">**Library:** None</span></span>  
<span data-ttu-id="65a0e-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="65a0e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="65a0e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="65a0e-122">See also</span></span>

- [<span data-ttu-id="65a0e-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="65a0e-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="65a0e-124">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="65a0e-124">Debugging Interfaces</span></span>](debugging-interfaces.md)

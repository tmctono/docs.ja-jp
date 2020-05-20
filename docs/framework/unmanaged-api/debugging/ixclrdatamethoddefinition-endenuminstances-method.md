---
title: 'IXCLRDataMethodDefinition:: EndEnumInstances メソッド'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7271c9594a679af205c404f59ff6731821aa0acf
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420995"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="931b2-102">IXCLRDataMethodDefinition:: EndEnumInstances メソッド</span><span class="sxs-lookup"><span data-stu-id="931b2-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="931b2-103">インスタンスの列挙中に使用される内部反復子によって使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="931b2-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="931b2-104">構文</span><span class="sxs-lookup"><span data-stu-id="931b2-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="931b2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="931b2-105">Parameters</span></span>

`handle`\
<span data-ttu-id="931b2-106">入出力インスタンスを列挙するハンドル。</span><span class="sxs-lookup"><span data-stu-id="931b2-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="931b2-107">解説</span><span class="sxs-lookup"><span data-stu-id="931b2-107">Remarks</span></span>

<span data-ttu-id="931b2-108">指定されたメソッドはインターフェイスの一部で `IXCLRDataMethodDefinition` あり、仮想メソッドテーブルの7番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="931b2-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 7th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="931b2-109">要件</span><span class="sxs-lookup"><span data-stu-id="931b2-109">Requirements</span></span>

<span data-ttu-id="931b2-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="931b2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="931b2-111">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="931b2-111">**Header:** None</span></span>  
<span data-ttu-id="931b2-112">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="931b2-112">**Library:** None</span></span>  
<span data-ttu-id="931b2-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="931b2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="931b2-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="931b2-114">See also</span></span>

- [<span data-ttu-id="931b2-115">デバッグ</span><span class="sxs-lookup"><span data-stu-id="931b2-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="931b2-116">IXCLRDataMethodDefinition インターフェイス</span><span class="sxs-lookup"><span data-stu-id="931b2-116">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)

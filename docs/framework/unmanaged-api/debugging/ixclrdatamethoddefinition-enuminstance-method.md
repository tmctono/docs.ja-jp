---
title: 'IXCLRDataMethodDefinition:: EnumInstance メソッド'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 72560de9777b2d826418e63b4a4fcccf1e4fa8b9
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396480"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="36073-102">IXCLRDataMethodDefinition:: EnumInstance メソッド</span><span class="sxs-lookup"><span data-stu-id="36073-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="36073-103">このメソッド定義のインスタンスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="36073-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="36073-104">構文</span><span class="sxs-lookup"><span data-stu-id="36073-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="36073-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="36073-105">Parameters</span></span>

`handle`\
<span data-ttu-id="36073-106">[入力、出力]インスタンスを列挙するハンドル。</span><span class="sxs-lookup"><span data-stu-id="36073-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="36073-107">入出力列挙されたインスタンス。</span><span class="sxs-lookup"><span data-stu-id="36073-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="36073-108">解説</span><span class="sxs-lookup"><span data-stu-id="36073-108">Remarks</span></span>

<span data-ttu-id="36073-109">指定されたメソッドはインターフェイスの一部で `IXCLRDataMethodDefinition` あり、仮想メソッドテーブルの6番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="36073-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 6th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="36073-110">要件</span><span class="sxs-lookup"><span data-stu-id="36073-110">Requirements</span></span>

<span data-ttu-id="36073-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36073-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="36073-112">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="36073-112">**Header:** None</span></span>  
<span data-ttu-id="36073-113">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="36073-113">**Library:** None</span></span>  
<span data-ttu-id="36073-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="36073-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="36073-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="36073-115">See also</span></span>

- [<span data-ttu-id="36073-116">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="36073-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="36073-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="36073-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="36073-118">IXCLRDataMethodDefinition インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36073-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="36073-119">IXCLRDataMethodInstance インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36073-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)

---
title: IXCLRDataMethodDefinition::EnumInstance メソッド
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
ms.openlocfilehash: dacf76582916ad50f51ae7c8818b496f31f9553e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353115"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="1f2be-102">IXCLRDataMethodDefinition::EnumInstance メソッド</span><span class="sxs-lookup"><span data-stu-id="1f2be-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="1f2be-103">このメソッドの定義のインスタンスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="1f2be-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1f2be-104">構文</span><span class="sxs-lookup"><span data-stu-id="1f2be-104">Syntax</span></span>

```
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="1f2be-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f2be-105">Parameters</span></span>

`handle`\
<span data-ttu-id="1f2be-106">[入力、出力]インスタンスを列挙するためのハンドル。</span><span class="sxs-lookup"><span data-stu-id="1f2be-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="1f2be-107">[out]列挙型のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="1f2be-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="1f2be-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="1f2be-108">Remarks</span></span>

<span data-ttu-id="1f2be-109">指定されたメソッドは、`IXCLRDataMethodDefinition`インターフェイスし、仮想メソッド テーブルの 4 番目のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="1f2be-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="1f2be-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="1f2be-110">Requirements</span></span>

<span data-ttu-id="1f2be-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f2be-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1f2be-112">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="1f2be-112">**Header:** None</span></span>  
<span data-ttu-id="1f2be-113">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="1f2be-113">**Library:** None</span></span>  
<span data-ttu-id="1f2be-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1f2be-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1f2be-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f2be-115">See also</span></span>

- [<span data-ttu-id="1f2be-116">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="1f2be-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="1f2be-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="1f2be-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="1f2be-118">IXCLRDataMethodDefinition インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f2be-118">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="1f2be-119">IXCLRDataMethodInstance インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f2be-119">IXCLRDataMethodInstance Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)

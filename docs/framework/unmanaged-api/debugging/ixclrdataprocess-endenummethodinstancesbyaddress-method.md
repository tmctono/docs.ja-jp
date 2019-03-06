---
title: IXCLRDataProcess::EndEnumMethodInstancesByAddress メソッド
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 072e775d11d44dfbca27f1616889e388ae61d467
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365998"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="a1372-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="a1372-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="a1372-103">インスタンスの列挙中に使用される内部の反復子によって使用されるリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="a1372-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a1372-104">構文</span><span class="sxs-lookup"><span data-stu-id="a1372-104">Syntax</span></span>

```
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="a1372-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1372-105">Parameters</span></span>

`handle`\
<span data-ttu-id="a1372-106">[out]メソッド インスタンスを列挙するためのハンドル。</span><span class="sxs-lookup"><span data-stu-id="a1372-106">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1372-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="a1372-107">Remarks</span></span>

<span data-ttu-id="a1372-108">指定されたメソッドは、`IXCLRDataProcess`インターフェイスし、仮想メソッド テーブルの 29 のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a1372-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a1372-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1372-109">Requirements</span></span>

<span data-ttu-id="a1372-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1372-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a1372-111">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="a1372-111">**Header:** None</span></span>  
<span data-ttu-id="a1372-112">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="a1372-112">**Library:** None</span></span>  
<span data-ttu-id="a1372-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a1372-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a1372-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1372-114">See also</span></span>

- [<span data-ttu-id="a1372-115">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="a1372-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="a1372-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="a1372-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="a1372-117">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1372-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)

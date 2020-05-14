---
title: 'IXCLRDataMethodInstance:: GetRepresentativeEntryAddress メソッド'
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: d9f9e16d243c0f3b45ac24776caea5bb9c32dcc1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395748"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="b1099-102">IXCLRDataMethodInstance:: GetRepresentativeEntryAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="b1099-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="b1099-103">メソッドに対して使用可能なすべてのエントリポイントのネイティブコンパイルを行うための最も代表的なエントリポイントアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b1099-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b1099-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1099-104">Syntax</span></span>

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="b1099-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1099-105">Parameters</span></span>

`addr`\
<span data-ttu-id="b1099-106">入出力メソッドの最も代表的なネイティブエントリポイントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="b1099-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1099-107">解説</span><span class="sxs-lookup"><span data-stu-id="b1099-107">Remarks</span></span>

<span data-ttu-id="b1099-108">指定されたメソッドは[ `IXCLRDataMethodInstance` インターフェイス](ixclrdatamethodinstance-interface.md)の一部であり、仮想メソッドテーブルの20番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="b1099-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 20th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b1099-109">要件</span><span class="sxs-lookup"><span data-stu-id="b1099-109">Requirements</span></span>

<span data-ttu-id="b1099-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1099-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b1099-111">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="b1099-111">**Header:** None</span></span>  
<span data-ttu-id="b1099-112">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="b1099-112">**Library:** None</span></span>  
<span data-ttu-id="b1099-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b1099-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b1099-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1099-114">See also</span></span>

- [<span data-ttu-id="b1099-115">デバッグ</span><span class="sxs-lookup"><span data-stu-id="b1099-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="b1099-116">IXCLRDataMethodInstance インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1099-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)

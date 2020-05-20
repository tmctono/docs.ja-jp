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
ms.openlocfilehash: d546cda5c68732e75550a3de286089f7df261c91
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420904"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="497a5-102">IXCLRDataMethodInstance:: GetRepresentativeEntryAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="497a5-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="497a5-103">メソッドに対して使用可能なすべてのエントリポイントのネイティブコンパイルを行うための最も代表的なエントリポイントアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="497a5-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="497a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="497a5-104">Syntax</span></span>

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="497a5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="497a5-105">Parameters</span></span>

`addr`\
<span data-ttu-id="497a5-106">入出力メソッドの最も代表的なネイティブエントリポイントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="497a5-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="497a5-107">解説</span><span class="sxs-lookup"><span data-stu-id="497a5-107">Remarks</span></span>

<span data-ttu-id="497a5-108">指定されたメソッドは[ `IXCLRDataMethodInstance` インターフェイス](ixclrdatamethodinstance-interface.md)の一部であり、仮想メソッドテーブルの20番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="497a5-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 20th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="497a5-109">要件</span><span class="sxs-lookup"><span data-stu-id="497a5-109">Requirements</span></span>

<span data-ttu-id="497a5-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="497a5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="497a5-111">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="497a5-111">**Header:** None</span></span>  
<span data-ttu-id="497a5-112">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="497a5-112">**Library:** None</span></span>  
<span data-ttu-id="497a5-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="497a5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="497a5-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="497a5-114">See also</span></span>

- [<span data-ttu-id="497a5-115">デバッグ</span><span class="sxs-lookup"><span data-stu-id="497a5-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="497a5-116">IXCLRDataMethodInstance インターフェイス</span><span class="sxs-lookup"><span data-stu-id="497a5-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)

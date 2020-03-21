---
title: メソッドをメソッドとして使用します。
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: afc5fc377dd45d5e8d4d2d7b3385ca0524df69e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176657"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="f5598-102">メソッドをメソッドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="f5598-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="f5598-103">アドレス オフセットから開始するこのプロセスのメソッド インスタンスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="f5598-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f5598-104">構文</span><span class="sxs-lookup"><span data-stu-id="f5598-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="f5598-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5598-105">Parameters</span></span>

`handle`\
<span data-ttu-id="f5598-106">[in]メソッド インスタンスを列挙するためのハンドル。</span><span class="sxs-lookup"><span data-stu-id="f5598-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="f5598-107">[アウト]列挙されたメソッド のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="f5598-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="f5598-108">解説</span><span class="sxs-lookup"><span data-stu-id="f5598-108">Remarks</span></span>

<span data-ttu-id="f5598-109">提供されたメソッドはインターフェイスの`IXCLRDataProcess`一部であり、仮想メソッド テーブルの 28 番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="f5598-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="f5598-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f5598-110">Requirements</span></span>

<span data-ttu-id="f5598-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5598-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="f5598-112">**ヘッダー:** なし**ライブラリ:** なし **.NET フレームワークのバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f5598-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f5598-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5598-113">See also</span></span>

- [<span data-ttu-id="f5598-114">列挙型</span><span class="sxs-lookup"><span data-stu-id="f5598-114">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="f5598-115">デバッグ</span><span class="sxs-lookup"><span data-stu-id="f5598-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="f5598-116">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f5598-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)

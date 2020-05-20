---
title: 'IXCLRDataProcess:: GetAppDomainByUniqueId メソッド'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
helpviewer.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: bb02ffed09cbcc31e653bfd3165050c247908c5d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420786"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="9926d-102">IXCLRDataProcess:: GetAppDomainByUniqueId メソッド</span><span class="sxs-lookup"><span data-stu-id="9926d-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="9926d-103">一意の `AppDomain` 識別子に基づいて、プロセス内のを取得します。</span><span class="sxs-lookup"><span data-stu-id="9926d-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9926d-104">構文</span><span class="sxs-lookup"><span data-stu-id="9926d-104">Syntax</span></span>

```cpp
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a><span data-ttu-id="9926d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9926d-105">Parameters</span></span>

`id`\
<span data-ttu-id="9926d-106">からAppDomain の一意識別子</span><span class="sxs-lookup"><span data-stu-id="9926d-106">[in] The unique identifier of the AppDomain</span></span>

`appDomain`\
<span data-ttu-id="9926d-107">入出力AppDomain</span><span class="sxs-lookup"><span data-stu-id="9926d-107">[out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="9926d-108">解説</span><span class="sxs-lookup"><span data-stu-id="9926d-108">Remarks</span></span>

<span data-ttu-id="9926d-109">指定されたメソッドはインターフェイスの一部で `IXCLRDataProcess` あり、仮想メソッドテーブルの20番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="9926d-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="9926d-110">返されるは、 `IXCLRDataAppDomain*` 他の api との対話に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9926d-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="9926d-111">要件</span><span class="sxs-lookup"><span data-stu-id="9926d-111">Requirements</span></span>

<span data-ttu-id="9926d-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9926d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="9926d-113">**ヘッダー:** None **Library:** None **.NET Framework バージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9926d-113">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9926d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9926d-114">See also</span></span>

- [<span data-ttu-id="9926d-115">デバッグ</span><span class="sxs-lookup"><span data-stu-id="9926d-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="9926d-116">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9926d-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)

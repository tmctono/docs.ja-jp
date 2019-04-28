---
title: IXCLRDataProcess::GetAppDomainByUniqueId メソッド
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
ms.openlocfilehash: 8b468d40ef8eb523ba8881627fae15cf9b7c7b80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775266"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="fa86b-102">IXCLRDataProcess::GetAppDomainByUniqueId メソッド</span><span class="sxs-lookup"><span data-stu-id="fa86b-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="fa86b-103">取得、`AppDomain`の一意の識別子に基づくプロセスにします。</span><span class="sxs-lookup"><span data-stu-id="fa86b-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="fa86b-104">構文</span><span class="sxs-lookup"><span data-stu-id="fa86b-104">Syntax</span></span>

```cpp
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a><span data-ttu-id="fa86b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa86b-105">Parameters</span></span>

`id`\
<span data-ttu-id="fa86b-106">[in]AppDomain の一意の識別子</span><span class="sxs-lookup"><span data-stu-id="fa86b-106">[in] The unique identifier of the AppDomain</span></span>

`appDomain`\
<span data-ttu-id="fa86b-107">[out]AppDomain</span><span class="sxs-lookup"><span data-stu-id="fa86b-107">[out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="fa86b-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="fa86b-108">Remarks</span></span>

<span data-ttu-id="fa86b-109">指定されたメソッドは、`IXCLRDataProcess`インターフェイスし、仮想メソッド テーブルの 20 のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="fa86b-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="fa86b-110">`IXCLRDataAppDomain*`返されるその他の Api との対話のために使用します。</span><span class="sxs-lookup"><span data-stu-id="fa86b-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="fa86b-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="fa86b-111">Requirements</span></span>

<span data-ttu-id="fa86b-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa86b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="fa86b-113">**ヘッダー:** None**ライブラリ。** None **.NET Framework のバージョン。** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fa86b-113">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="fa86b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa86b-114">See also</span></span>

- [<span data-ttu-id="fa86b-115">デバッグ</span><span class="sxs-lookup"><span data-stu-id="fa86b-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="fa86b-116">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa86b-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)

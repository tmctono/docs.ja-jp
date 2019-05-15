---
title: IXCLRDataModule::GetVersionId メソッド
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetVersionId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetVersionId Method
helpviewer.keywords:
- IXCLRDataModule::GetVersionId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 6ec18bcf079c7687df4ac9b7c5db23b84383c517
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632306"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="66bd3-102">IXCLRDataModule::GetVersionId メソッド</span><span class="sxs-lookup"><span data-stu-id="66bd3-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="66bd3-103">モジュールのバージョン識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="66bd3-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="66bd3-104">構文</span><span class="sxs-lookup"><span data-stu-id="66bd3-104">Syntax</span></span>

```
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="66bd3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="66bd3-105">Parameters</span></span>

`vid`\
<span data-ttu-id="66bd3-106">[out]モジュールのバージョンの識別子です。</span><span class="sxs-lookup"><span data-stu-id="66bd3-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="66bd3-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="66bd3-107">Remarks</span></span>

<span data-ttu-id="66bd3-108">指定されたメソッドは、`IXCLRDataModule`インターフェイスし、40 のスロットの仮想メソッド テーブルに対応しています。</span><span class="sxs-lookup"><span data-stu-id="66bd3-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 40th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="66bd3-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="66bd3-109">Requirements</span></span>

<span data-ttu-id="66bd3-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66bd3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="66bd3-111">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="66bd3-111">**Header:** None</span></span>  
<span data-ttu-id="66bd3-112">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="66bd3-112">**Library:** None</span></span>  
<span data-ttu-id="66bd3-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="66bd3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="66bd3-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="66bd3-114">See also</span></span>

- [<span data-ttu-id="66bd3-115">デバッグ</span><span class="sxs-lookup"><span data-stu-id="66bd3-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="66bd3-116">IXCLRDataModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="66bd3-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

---
title: 'IXCLRDataModule:: GetVersionId メソッド'
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
ms.openlocfilehash: 9d5ef137a5d76c3d7545ab16921352123e978fb1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420865"
---
# <a name="ixclrdatamodulegetversionid-method"></a><span data-ttu-id="29cf5-102">IXCLRDataModule:: GetVersionId メソッド</span><span class="sxs-lookup"><span data-stu-id="29cf5-102">IXCLRDataModule::GetVersionId Method</span></span>

<span data-ttu-id="29cf5-103">モジュールのバージョン識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="29cf5-103">Gets the module's version identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="29cf5-104">構文</span><span class="sxs-lookup"><span data-stu-id="29cf5-104">Syntax</span></span>

```cpp
HRESULT GetVersionId(
    [out] GUID* vid
);
```

## <a name="parameters"></a><span data-ttu-id="29cf5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="29cf5-105">Parameters</span></span>

`vid`\
<span data-ttu-id="29cf5-106">入出力モジュールのバージョン識別子。</span><span class="sxs-lookup"><span data-stu-id="29cf5-106">[out] The module's version identifier.</span></span>

## <a name="remarks"></a><span data-ttu-id="29cf5-107">解説</span><span class="sxs-lookup"><span data-stu-id="29cf5-107">Remarks</span></span>

<span data-ttu-id="29cf5-108">指定されたメソッドはインターフェイスの一部で `IXCLRDataModule` あり、仮想メソッドテーブルの4番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="29cf5-108">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 41st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="29cf5-109">要件</span><span class="sxs-lookup"><span data-stu-id="29cf5-109">Requirements</span></span>

<span data-ttu-id="29cf5-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29cf5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="29cf5-111">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="29cf5-111">**Header:** None</span></span>  
<span data-ttu-id="29cf5-112">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="29cf5-112">**Library:** None</span></span>  
<span data-ttu-id="29cf5-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="29cf5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="29cf5-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="29cf5-114">See also</span></span>

- [<span data-ttu-id="29cf5-115">デバッグ</span><span class="sxs-lookup"><span data-stu-id="29cf5-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="29cf5-116">IXCLRDataModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29cf5-116">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

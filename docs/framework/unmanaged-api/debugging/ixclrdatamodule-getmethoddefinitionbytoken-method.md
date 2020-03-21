---
title: メソッドメソッドを使用します。
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetMethodDefinitionByToken Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method
helpviewer.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 294c5340caf2217f9337d654a11a63a43d46febd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176670"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="c1fdc-102">メソッドメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c1fdc-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="c1fdc-103">指定したメタデータ トークンに対応するメソッド定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="c1fdc-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c1fdc-104">構文</span><span class="sxs-lookup"><span data-stu-id="c1fdc-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="c1fdc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c1fdc-105">Parameters</span></span>

`token`\
<span data-ttu-id="c1fdc-106">[in]メソッド トークン。</span><span class="sxs-lookup"><span data-stu-id="c1fdc-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="c1fdc-107">[アウト]メソッド定義。</span><span class="sxs-lookup"><span data-stu-id="c1fdc-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1fdc-108">解説</span><span class="sxs-lookup"><span data-stu-id="c1fdc-108">Remarks</span></span>

<span data-ttu-id="c1fdc-109">提供されたメソッドはインターフェイスの`IXCLRDataModule`一部であり、仮想メソッド テーブルの 25 番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="c1fdc-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="c1fdc-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="c1fdc-110">Requirements</span></span>

<span data-ttu-id="c1fdc-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1fdc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c1fdc-112">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="c1fdc-112">**Header:** None</span></span>  
<span data-ttu-id="c1fdc-113">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="c1fdc-113">**Library:** None</span></span>  
<span data-ttu-id="c1fdc-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c1fdc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c1fdc-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1fdc-115">See also</span></span>

- [<span data-ttu-id="c1fdc-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="c1fdc-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="c1fdc-117">IXCLRDataModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1fdc-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

---
title: IXCLRDataModule::GetMethodDefinitionByToken メソッド
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
ms.openlocfilehash: 2c0cf56f108396226b7c7399f6da75e5f47d36f3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744668"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="b2c4b-102">IXCLRDataModule::GetMethodDefinitionByToken メソッド</span><span class="sxs-lookup"><span data-stu-id="b2c4b-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="b2c4b-103">指定したメタデータ トークンに対応するメソッドの定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2c4b-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b2c4b-104">構文</span><span class="sxs-lookup"><span data-stu-id="b2c4b-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="b2c4b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b2c4b-105">Parameters</span></span>

`token`\
<span data-ttu-id="b2c4b-106">[in]メソッド トークンです。</span><span class="sxs-lookup"><span data-stu-id="b2c4b-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="b2c4b-107">[out]メソッドの定義。</span><span class="sxs-lookup"><span data-stu-id="b2c4b-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2c4b-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="b2c4b-108">Remarks</span></span>

<span data-ttu-id="b2c4b-109">指定されたメソッドは、`IXCLRDataModule`インターフェイスし、仮想メソッド テーブルの 25 のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="b2c4b-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b2c4b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="b2c4b-110">Requirements</span></span>

<span data-ttu-id="b2c4b-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c4b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b2c4b-112">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="b2c4b-112">**Header:** None</span></span>  
<span data-ttu-id="b2c4b-113">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="b2c4b-113">**Library:** None</span></span>  
<span data-ttu-id="b2c4b-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b2c4b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="b2c4b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2c4b-115">See also</span></span>

- [<span data-ttu-id="b2c4b-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="b2c4b-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="b2c4b-117">IXCLRDataModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2c4b-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

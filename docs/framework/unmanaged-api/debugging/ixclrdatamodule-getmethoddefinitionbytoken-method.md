---
title: 'IXCLRDataModule:: GetMethodDefinitionByToken メソッド'
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
ms.openlocfilehash: c70920205b27376d453bdd0a13223c6a5569075b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395297"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="fa651-102">IXCLRDataModule:: GetMethodDefinitionByToken メソッド</span><span class="sxs-lookup"><span data-stu-id="fa651-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="fa651-103">指定されたメタデータトークンに対応するメソッド定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa651-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="fa651-104">構文</span><span class="sxs-lookup"><span data-stu-id="fa651-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="fa651-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa651-105">Parameters</span></span>

`token`\
<span data-ttu-id="fa651-106">からメソッドトークン。</span><span class="sxs-lookup"><span data-stu-id="fa651-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="fa651-107">入出力メソッドの定義。</span><span class="sxs-lookup"><span data-stu-id="fa651-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa651-108">解説</span><span class="sxs-lookup"><span data-stu-id="fa651-108">Remarks</span></span>

<span data-ttu-id="fa651-109">指定されたメソッドはインターフェイスの一部で `IXCLRDataModule` あり、仮想メソッドテーブルの26日スロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="fa651-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="fa651-110">要件</span><span class="sxs-lookup"><span data-stu-id="fa651-110">Requirements</span></span>

<span data-ttu-id="fa651-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa651-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="fa651-112">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="fa651-112">**Header:** None</span></span>  
<span data-ttu-id="fa651-113">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="fa651-113">**Library:** None</span></span>  
<span data-ttu-id="fa651-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fa651-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fa651-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa651-115">See also</span></span>

- [<span data-ttu-id="fa651-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="fa651-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="fa651-117">IXCLRDataModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa651-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)

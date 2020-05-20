---
title: 'IXCLRDataMethodDefinition:: StartEnumInstances メソッド'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: b0c37c666f23f04239ed827246b87c43ee8d5ad9
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420930"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="30cef-102">IXCLRDataMethodDefinition:: StartEnumInstances メソッド</span><span class="sxs-lookup"><span data-stu-id="30cef-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="30cef-103">指定されたのメソッドインスタンスの列挙体のハンドルを提供 `IXCLRDataAppDomain` します。</span><span class="sxs-lookup"><span data-stu-id="30cef-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="30cef-104">構文</span><span class="sxs-lookup"><span data-stu-id="30cef-104">Syntax</span></span>

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="30cef-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="30cef-105">Parameters</span></span>

`appDomain`\
<span data-ttu-id="30cef-106">から列挙型の AppDomain。</span><span class="sxs-lookup"><span data-stu-id="30cef-106">[in] An AppDomain for the enumeration.</span></span>

`handle`\
<span data-ttu-id="30cef-107">入出力インスタンスを列挙するハンドル。</span><span class="sxs-lookup"><span data-stu-id="30cef-107">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="30cef-108">解説</span><span class="sxs-lookup"><span data-stu-id="30cef-108">Remarks</span></span>

<span data-ttu-id="30cef-109">指定されたメソッドはインターフェイスの一部で `IXCLRDataMethodDefinition` あり、仮想メソッドテーブルの5番目のスロットに対応します。</span><span class="sxs-lookup"><span data-stu-id="30cef-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 5th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="30cef-110">要件</span><span class="sxs-lookup"><span data-stu-id="30cef-110">Requirements</span></span>

<span data-ttu-id="30cef-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30cef-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="30cef-112">**ヘッダー:** 存在</span><span class="sxs-lookup"><span data-stu-id="30cef-112">**Header:** None</span></span>  
<span data-ttu-id="30cef-113">**ライブラリ:** 存在</span><span class="sxs-lookup"><span data-stu-id="30cef-113">**Library:** None</span></span>  
<span data-ttu-id="30cef-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="30cef-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="30cef-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="30cef-115">See also</span></span>

- [<span data-ttu-id="30cef-116">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="30cef-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="30cef-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="30cef-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="30cef-118">IXCLRDataMethodDefinition インターフェイス</span><span class="sxs-lookup"><span data-stu-id="30cef-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)

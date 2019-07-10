---
title: InheritsFrom 関数 (アンマネージ API リファレンス)
description: InheritsFrom 関数では、クラスまたはインスタンスが特定の親クラスから派生するかどうかを決定します。
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c04a08c9712359453b9c5a9d136e22e1de8648a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746508"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="051aa-103">InheritsFrom 関数</span><span class="sxs-lookup"><span data-stu-id="051aa-103">InheritsFrom function</span></span>
<span data-ttu-id="051aa-104">指定した親クラスから現在のクラスまたはインスタンスが派生しているかどうかが判定されます。</span><span class="sxs-lookup"><span data-stu-id="051aa-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="051aa-105">構文</span><span class="sxs-lookup"><span data-stu-id="051aa-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="051aa-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="051aa-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="051aa-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="051aa-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="051aa-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="051aa-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="051aa-109">[in]クラスの名前。</span><span class="sxs-lookup"><span data-stu-id="051aa-109">[in] The name of the class.</span></span> <span data-ttu-id="051aa-110">`wszAncestor` 有効なをポイントする必要があります`LPCWSTR`します。</span><span class="sxs-lookup"><span data-stu-id="051aa-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="051aa-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="051aa-111">Return value</span></span>

<span data-ttu-id="051aa-112">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="051aa-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="051aa-113">定数</span><span class="sxs-lookup"><span data-stu-id="051aa-113">Constant</span></span>  |<span data-ttu-id="051aa-114">値</span><span class="sxs-lookup"><span data-stu-id="051aa-114">Value</span></span>  |<span data-ttu-id="051aa-115">説明</span><span class="sxs-lookup"><span data-stu-id="051aa-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="051aa-116">0</span><span class="sxs-lookup"><span data-stu-id="051aa-116">0</span></span> | <span data-ttu-id="051aa-117">現在のオブジェクトが継承`wszAncestor`します。</span><span class="sxs-lookup"><span data-stu-id="051aa-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="051aa-118">1</span><span class="sxs-lookup"><span data-stu-id="051aa-118">1</span></span> | <span data-ttu-id="051aa-119">現在のオブジェクトを継承しない`wszAncestor`します。</span><span class="sxs-lookup"><span data-stu-id="051aa-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="051aa-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="051aa-120">0x80041008</span></span> | <span data-ttu-id="051aa-121">`wszAncestor` は `null` です。</span><span class="sxs-lookup"><span data-stu-id="051aa-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="051aa-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="051aa-122">Remarks</span></span>

<span data-ttu-id="051aa-123">この関数の呼び出しをラップする、 [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom)メソッド。</span><span class="sxs-lookup"><span data-stu-id="051aa-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="051aa-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="051aa-124">Requirements</span></span>  
 <span data-ttu-id="051aa-125">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="051aa-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="051aa-126">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="051aa-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="051aa-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="051aa-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="051aa-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="051aa-128">See also</span></span>

- [<span data-ttu-id="051aa-129">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="051aa-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

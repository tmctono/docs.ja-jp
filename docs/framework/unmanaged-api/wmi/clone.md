---
title: クローン関数 (アンマネージ API リファレンス)
description: Clone 関数は、現在のオブジェクトの完全なクローンである新しいオブジェクトを返します。
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: cb4951a1f289417482bfa1287028cc66349a5938
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176852"
---
# <a name="clone-function"></a><span data-ttu-id="414cc-103">Clone 関数</span><span class="sxs-lookup"><span data-stu-id="414cc-103">Clone function</span></span>
<span data-ttu-id="414cc-104">現在のオブジェクトの完全な複製である新しいオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="414cc-104">Returns a new object that is a complete clone of the current object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="414cc-105">構文</span><span class="sxs-lookup"><span data-stu-id="414cc-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [out] IWbemClassObject**  ppCopy
);
```  

## <a name="parameters"></a><span data-ttu-id="414cc-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="414cc-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="414cc-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="414cc-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="414cc-108">[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="414cc-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="414cc-109">[アウト]の完全な孤独である新しいオブジェクト`ptr`。</span><span class="sxs-lookup"><span data-stu-id="414cc-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="414cc-110">この引数は、`null`現在のオブジェクトのコピーを受け取った場合は使用できません。</span><span class="sxs-lookup"><span data-stu-id="414cc-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="414cc-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="414cc-111">Return value</span></span>

<span data-ttu-id="414cc-112">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="414cc-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="414cc-113">常時</span><span class="sxs-lookup"><span data-stu-id="414cc-113">Constant</span></span>  |<span data-ttu-id="414cc-114">Value</span><span class="sxs-lookup"><span data-stu-id="414cc-114">Value</span></span>  |<span data-ttu-id="414cc-115">説明</span><span class="sxs-lookup"><span data-stu-id="414cc-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="414cc-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="414cc-116">0x80041001</span></span> | <span data-ttu-id="414cc-117">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="414cc-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="414cc-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="414cc-118">0x80041008</span></span> | <span data-ttu-id="414cc-119">`null`はパラメータとして指定されており、この使用法では有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="414cc-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="414cc-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="414cc-120">0x80041006</span></span> | <span data-ttu-id="414cc-121">メモリ不足でオブジェクトのクローンを作成できません。</span><span class="sxs-lookup"><span data-stu-id="414cc-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="414cc-122">0</span><span class="sxs-lookup"><span data-stu-id="414cc-122">0</span></span> | <span data-ttu-id="414cc-123">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="414cc-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="414cc-124">解説</span><span class="sxs-lookup"><span data-stu-id="414cc-124">Remarks</span></span>

<span data-ttu-id="414cc-125">この関数は、メソッドの呼び出しをラップ[します](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)。</span><span class="sxs-lookup"><span data-stu-id="414cc-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="414cc-126">複製されたオブジェクトは、参照カウントが 1 の COM オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="414cc-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="414cc-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="414cc-127">Requirements</span></span>  
 <span data-ttu-id="414cc-128">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="414cc-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="414cc-129">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="414cc-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="414cc-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="414cc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="414cc-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="414cc-131">See also</span></span>

- [<span data-ttu-id="414cc-132">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="414cc-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

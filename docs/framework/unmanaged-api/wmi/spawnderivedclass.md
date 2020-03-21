---
title: 関数 (アンマネージ API リファレンス)
description: 関数は、オブジェクトから派生する新しいオブジェクトを作成します。
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: e9784f8a024c788823dc702794b2b86eea1827bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174850"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="56693-103">SpawnDerivedClass 関数</span><span class="sxs-lookup"><span data-stu-id="56693-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="56693-104">指定したオブジェクトから新たに派生するクラス オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="56693-104">Creates a newly derived class object from a specified object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="56693-105">構文</span><span class="sxs-lookup"><span data-stu-id="56693-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass);
```  

## <a name="parameters"></a><span data-ttu-id="56693-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="56693-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="56693-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="56693-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="56693-108">[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="56693-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="56693-109">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="56693-109">[in] Reserved.</span></span> <span data-ttu-id="56693-110">このパラメーターは 0 でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="56693-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="56693-111">[アウト]新しいクラス定義オブジェクトへのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="56693-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="56693-112">エラーが発生した場合、新しいオブジェクトは返されず、`ppNewClass`変更されません。</span><span class="sxs-lookup"><span data-stu-id="56693-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="56693-113">その値を指定`null`することはできません。</span><span class="sxs-lookup"><span data-stu-id="56693-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="56693-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="56693-114">Return value</span></span>

<span data-ttu-id="56693-115">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="56693-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="56693-116">常時</span><span class="sxs-lookup"><span data-stu-id="56693-116">Constant</span></span>  |<span data-ttu-id="56693-117">Value</span><span class="sxs-lookup"><span data-stu-id="56693-117">Value</span></span>  |<span data-ttu-id="56693-118">説明</span><span class="sxs-lookup"><span data-stu-id="56693-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="56693-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="56693-119">0x80041001</span></span> | <span data-ttu-id="56693-120">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="56693-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="56693-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="56693-121">0x80041016</span></span> | <span data-ttu-id="56693-122">インスタンスからクラスを生成するなどの無効な操作が要求されました。</span><span class="sxs-lookup"><span data-stu-id="56693-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="56693-123">ソース クラスが完全に定義されていないか、Windows の管理に登録されていないので、新しい派生クラスは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="56693-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="56693-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="56693-124">0x80041006</span></span> | <span data-ttu-id="56693-125">メモリ不足のため、操作を完了できません。</span><span class="sxs-lookup"><span data-stu-id="56693-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="56693-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="56693-126">0x80041008</span></span> | <span data-ttu-id="56693-127">`ppNewClass` は `null` です。</span><span class="sxs-lookup"><span data-stu-id="56693-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="56693-128">0</span><span class="sxs-lookup"><span data-stu-id="56693-128">0</span></span> | <span data-ttu-id="56693-129">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="56693-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="56693-130">解説</span><span class="sxs-lookup"><span data-stu-id="56693-130">Remarks</span></span>

<span data-ttu-id="56693-131">この関数は、メソッドの呼び出し[を](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)ラップします。</span><span class="sxs-lookup"><span data-stu-id="56693-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="56693-132">`ptr`は、スポーンされたオブジェクトの親クラスとなるクラス定義である必要があります。</span><span class="sxs-lookup"><span data-stu-id="56693-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="56693-133">返されたオブジェクトは、現在のオブジェクトのサブクラスになります。</span><span class="sxs-lookup"><span data-stu-id="56693-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="56693-134">返される新しいオブジェクト`ppNewClass`は、自動的に現在のオブジェクトのサブクラスになります。</span><span class="sxs-lookup"><span data-stu-id="56693-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="56693-135">この動作はオーバーライドできません。</span><span class="sxs-lookup"><span data-stu-id="56693-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="56693-136">サブクラス (派生クラス) を作成できるメソッドは他にありません。</span><span class="sxs-lookup"><span data-stu-id="56693-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="56693-137">必要条件</span><span class="sxs-lookup"><span data-stu-id="56693-137">Requirements</span></span>  
 <span data-ttu-id="56693-138">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56693-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56693-139">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="56693-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="56693-140">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="56693-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56693-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="56693-141">See also</span></span>

- [<span data-ttu-id="56693-142">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="56693-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

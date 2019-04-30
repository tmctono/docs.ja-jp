---
title: SpawnDerivedClass 関数 (アンマネージ API リファレンス)
description: SpawnDerivedClass 関数は、オブジェクトから派生した新しいオブジェクトを作成します。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81f4d5219865bf7f7c9e6d284d74d0c249729dfc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040535"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="da849-103">SpawnDerivedClass 関数</span><span class="sxs-lookup"><span data-stu-id="da849-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="da849-104">指定したオブジェクトから新たに派生するクラス オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="da849-104">Creates a newly derived class object from a specified object.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="da849-105">構文</span><span class="sxs-lookup"><span data-stu-id="da849-105">Syntax</span></span>  
  
```  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a><span data-ttu-id="da849-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da849-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="da849-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="da849-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="da849-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="da849-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="da849-109">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="da849-109">[in] Reserved.</span></span> <span data-ttu-id="da849-110">このパラメーターは、0 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da849-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="da849-111">[out]新しいクラス定義のオブジェクトへのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="da849-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="da849-112">新しいオブジェクトでないエラーが発生する場合、返されると`ppNewClass`は左未変更の状態します。</span><span class="sxs-lookup"><span data-stu-id="da849-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="da849-113">その値にすることはできません`null`します。</span><span class="sxs-lookup"><span data-stu-id="da849-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="da849-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="da849-114">Return value</span></span>

<span data-ttu-id="da849-115">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="da849-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="da849-116">定数</span><span class="sxs-lookup"><span data-stu-id="da849-116">Constant</span></span>  |<span data-ttu-id="da849-117">値</span><span class="sxs-lookup"><span data-stu-id="da849-117">Value</span></span>  |<span data-ttu-id="da849-118">説明</span><span class="sxs-lookup"><span data-stu-id="da849-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="da849-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="da849-119">0x80041001</span></span> | <span data-ttu-id="da849-120">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="da849-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="da849-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="da849-121">0x80041016</span></span> | <span data-ttu-id="da849-122">インスタンスからのクラスの生成などの無効な操作が要求されました。</span><span class="sxs-lookup"><span data-stu-id="da849-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="da849-123">ソース クラスが完全に定義されているか、Windows の管理を登録するため、新しい派生クラスは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="da849-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="da849-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="da849-124">0x80041006</span></span> | <span data-ttu-id="da849-125">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="da849-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="da849-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="da849-126">0x80041008</span></span> | <span data-ttu-id="da849-127">`ppNewClass` は `null`です。</span><span class="sxs-lookup"><span data-stu-id="da849-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="da849-128">0</span><span class="sxs-lookup"><span data-stu-id="da849-128">0</span></span> | <span data-ttu-id="da849-129">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="da849-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="da849-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="da849-130">Remarks</span></span>

<span data-ttu-id="da849-131">この関数の呼び出しをラップする、 [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)メソッド。</span><span class="sxs-lookup"><span data-stu-id="da849-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="da849-132">`ptr` 生成されたオブジェクトの親クラスとなるクラス定義である必要があります。</span><span class="sxs-lookup"><span data-stu-id="da849-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="da849-133">返されるオブジェクトでは、現在のオブジェクトのサブクラスになります。</span><span class="sxs-lookup"><span data-stu-id="da849-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="da849-134">返される新しいオブジェクト`ppNewClass`自動的に現在のオブジェクトのサブクラスになります。</span><span class="sxs-lookup"><span data-stu-id="da849-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="da849-135">この動作を上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="da849-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="da849-136">サブクラス (派生クラス) を作成できる他の方法はありません。</span><span class="sxs-lookup"><span data-stu-id="da849-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="da849-137">必要条件</span><span class="sxs-lookup"><span data-stu-id="da849-137">Requirements</span></span>  
 <span data-ttu-id="da849-138">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="da849-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da849-139">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="da849-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="da849-140">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="da849-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da849-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="da849-141">See also</span></span>

- [<span data-ttu-id="da849-142">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="da849-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

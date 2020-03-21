---
title: 関数 (アンマネージ API リファレンス)
description: 関数は、クラスの新しいインスタンスを作成します。
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: a15eb8123c1ee807444bdb4c6fe71cdccc08f434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176722"
---
# <a name="spawninstance-function"></a><span data-ttu-id="34abc-103">SpawnInstance 関数</span><span class="sxs-lookup"><span data-stu-id="34abc-103">SpawnInstance function</span></span>
<span data-ttu-id="34abc-104">クラスの新しいインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="34abc-104">Creates a new instance of a class.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="34abc-105">構文</span><span class="sxs-lookup"><span data-stu-id="34abc-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance);
```  

## <a name="parameters"></a><span data-ttu-id="34abc-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34abc-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="34abc-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="34abc-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="34abc-108">[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="34abc-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="34abc-109">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="34abc-109">[in] Reserved.</span></span> <span data-ttu-id="34abc-110">このパラメーターは 0 でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="34abc-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="34abc-111">[アウト]クラスの新しいインスタンスへのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="34abc-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="34abc-112">エラーが発生した場合、新しいオブジェクトは返されず、`ppNewInstance`変更されません。</span><span class="sxs-lookup"><span data-stu-id="34abc-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="34abc-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="34abc-113">Return value</span></span>

<span data-ttu-id="34abc-114">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="34abc-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="34abc-115">常時</span><span class="sxs-lookup"><span data-stu-id="34abc-115">Constant</span></span>  |<span data-ttu-id="34abc-116">Value</span><span class="sxs-lookup"><span data-stu-id="34abc-116">Value</span></span>  |<span data-ttu-id="34abc-117">説明</span><span class="sxs-lookup"><span data-stu-id="34abc-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="34abc-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="34abc-118">0x80041020</span></span> | <span data-ttu-id="34abc-119">`ptr`は有効なクラス定義ではないため、新しいインスタンスを生成できません。</span><span class="sxs-lookup"><span data-stu-id="34abc-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="34abc-120">不完全であるか、[または PutClassWmi](putclasswmi.md)を呼び出して Windows 管理に登録されていません。</span><span class="sxs-lookup"><span data-stu-id="34abc-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="34abc-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="34abc-121">0x80041006</span></span> | <span data-ttu-id="34abc-122">メモリ不足のため、操作を完了できません。</span><span class="sxs-lookup"><span data-stu-id="34abc-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="34abc-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="34abc-123">0x80041008</span></span> | <span data-ttu-id="34abc-124">`ppNewClass` は `null` です。</span><span class="sxs-lookup"><span data-stu-id="34abc-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="34abc-125">0</span><span class="sxs-lookup"><span data-stu-id="34abc-125">0</span></span> | <span data-ttu-id="34abc-126">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="34abc-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="34abc-127">解説</span><span class="sxs-lookup"><span data-stu-id="34abc-127">Remarks</span></span>

<span data-ttu-id="34abc-128">この関数は、メソッドの呼び出し[を](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance)ラップします。</span><span class="sxs-lookup"><span data-stu-id="34abc-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="34abc-129">`ptr`は、Windows 管理から取得したクラス定義である必要があります。</span><span class="sxs-lookup"><span data-stu-id="34abc-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="34abc-130">(インスタンスからのインスタンスの生成はサポートされていますが、返されるインスタンスは空です)。次に、このクラス定義を使用して新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="34abc-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="34abc-131">インスタンスを Windows 管理に書き込む場合は[、PutInstanceWmi](putinstancewmi.md)関数の呼び出しが必要です。</span><span class="sxs-lookup"><span data-stu-id="34abc-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>

<span data-ttu-id="34abc-132">返される新しいオブジェクト`ppNewClass`は、自動的に現在のオブジェクトのサブクラスになります。</span><span class="sxs-lookup"><span data-stu-id="34abc-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="34abc-133">この動作はオーバーライドできません。</span><span class="sxs-lookup"><span data-stu-id="34abc-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="34abc-134">サブクラス (派生クラス) を作成できるメソッドは他にありません。</span><span class="sxs-lookup"><span data-stu-id="34abc-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="34abc-135">必要条件</span><span class="sxs-lookup"><span data-stu-id="34abc-135">Requirements</span></span>  
 <span data-ttu-id="34abc-136">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34abc-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34abc-137">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="34abc-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="34abc-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="34abc-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34abc-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="34abc-139">See also</span></span>

- [<span data-ttu-id="34abc-140">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="34abc-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

---
title: プットメソッド関数 (アンマネージ API リファレンス)
description: メソッドを作成する関数です。
ms.date: 11/06/2017
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 93347b7290211b5d62829604678261fdf4da1ec3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174915"
---
# <a name="putmethod-function"></a><span data-ttu-id="dc659-103">PutMethod 関数</span><span class="sxs-lookup"><span data-stu-id="dc659-103">PutMethod function</span></span>
<span data-ttu-id="dc659-104">メソッドが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc659-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="dc659-105">構文</span><span class="sxs-lookup"><span data-stu-id="dc659-105">Syntax</span></span>  
  
```cpp  
HRESULT PutMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*  ptr,
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
);
```  

## <a name="parameters"></a><span data-ttu-id="dc659-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc659-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="dc659-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="dc659-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="dc659-108">[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dc659-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="dc659-109">[in]作成するメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="dc659-109">[in] The name of the method to create.</span></span>

`lFlags`  
<span data-ttu-id="dc659-110">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="dc659-110">[in] Reserved.</span></span> <span data-ttu-id="dc659-111">このパラメーターは 0 でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="dc659-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="dc659-112">[in]メソッドのパラメーターを格納している[__Parametersシステム クラス](/windows/desktop/WmiSdk/--parameters)の`in`コピーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="dc659-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="dc659-113">このパラメータは、 に`null`設定されている場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="dc659-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="dc659-114">[in] メソッドのパラメーターを格納している[__Parametersシステム クラス](/windows/desktop/WmiSdk/--parameters)の`out`コピーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="dc659-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="dc659-115">このパラメータは、 に`null`設定されている場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="dc659-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="dc659-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="dc659-116">Return value</span></span>

<span data-ttu-id="dc659-117">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="dc659-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="dc659-118">常時</span><span class="sxs-lookup"><span data-stu-id="dc659-118">Constant</span></span>  |<span data-ttu-id="dc659-119">Value</span><span class="sxs-lookup"><span data-stu-id="dc659-119">Value</span></span>  |<span data-ttu-id="dc659-120">説明</span><span class="sxs-lookup"><span data-stu-id="dc659-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="dc659-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="dc659-121">0x80041008</span></span> | <span data-ttu-id="dc659-122">1 つ以上のパラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="dc659-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="dc659-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="dc659-123">0x80041043</span></span> | <span data-ttu-id="dc659-124">pInSignature オブジェクトと`[in, out]` *pOutSignature* *pOutSignature*オブジェクトの両方で指定されたメソッド パラメーターには、異なる修飾子があります。</span><span class="sxs-lookup"><span data-stu-id="dc659-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="dc659-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="dc659-125">0x80041036</span></span> | <span data-ttu-id="dc659-126">メソッド パラメータに**ID**修飾子の指定がありません。</span><span class="sxs-lookup"><span data-stu-id="dc659-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="dc659-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="dc659-127">0x80041038</span></span> | <span data-ttu-id="dc659-128">メソッド パラメータに割り当てられた ID シリーズが連続していないか、0 から始まらない。</span><span class="sxs-lookup"><span data-stu-id="dc659-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="dc659-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="dc659-129">0x80041039</span></span> | <span data-ttu-id="dc659-130">メソッドの戻り値には**ID**修飾子があります。</span><span class="sxs-lookup"><span data-stu-id="dc659-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="dc659-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="dc659-131">0x80041034</span></span> | <span data-ttu-id="dc659-132">親クラスから既存のメソッド名を再利用しようとしましたが、シグネチャが一致しませんでした。</span><span class="sxs-lookup"><span data-stu-id="dc659-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="dc659-133">0</span><span class="sxs-lookup"><span data-stu-id="dc659-133">0</span></span> | <span data-ttu-id="dc659-134">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="dc659-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="dc659-135">解説</span><span class="sxs-lookup"><span data-stu-id="dc659-135">Remarks</span></span>

<span data-ttu-id="dc659-136">この関数は、メソッドの呼び出し[:Pをラップします](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)。</span><span class="sxs-lookup"><span data-stu-id="dc659-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="dc659-137">このメソッド呼び出しは`ptr`、CIM クラス定義の場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="dc659-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="dc659-138">メソッド操作は、CIM インスタンスを指す[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)ポインターからは使用できません。</span><span class="sxs-lookup"><span data-stu-id="dc659-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="dc659-139">ユーザーは、アンダースコアで始まる名前または末尾に名前を付けてメソッドを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc659-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="dc659-140">これは、システム クラスとプロパティ用に予約されています。</span><span class="sxs-lookup"><span data-stu-id="dc659-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="dc659-141">メソッドの場合、`in`および`out`パラメーターは[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)オブジェクトのプロパティとして記述されます。</span><span class="sxs-lookup"><span data-stu-id="dc659-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="dc659-142">パラメーター`[in/out]`は、`pInSignature`パラメーター`pOutSignature`が指すオブジェクトと の両方に同じプロパティを追加することで定義できます。</span><span class="sxs-lookup"><span data-stu-id="dc659-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="dc659-143">この場合、プロパティは同じ**ID**修飾子の値を共有します。</span><span class="sxs-lookup"><span data-stu-id="dc659-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="dc659-144">[__Parameters](/windows/desktop/WmiSdk/--parameters)クラス オブジェクトの各プロパティには`ReturnValue`**、ID**修飾子 (パラメーターが出現する順序を識別する 0 から始まる数値) が必要です。</span><span class="sxs-lookup"><span data-stu-id="dc659-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="dc659-145">2 つのパラメーターに同じ**ID**値を**ID**指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc659-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="dc659-146">いずれかの条件が発生した場合、`PutMethod`関数は`WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`を返します。</span><span class="sxs-lookup"><span data-stu-id="dc659-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="dc659-147">例</span><span class="sxs-lookup"><span data-stu-id="dc659-147">Example</span></span>

<span data-ttu-id="dc659-148">例については、メソッド[:P](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc659-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="dc659-149">必要条件</span><span class="sxs-lookup"><span data-stu-id="dc659-149">Requirements</span></span>  
 <span data-ttu-id="dc659-150">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc659-150">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc659-151">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="dc659-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="dc659-152">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dc659-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc659-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc659-153">See also</span></span>

- [<span data-ttu-id="dc659-154">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="dc659-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

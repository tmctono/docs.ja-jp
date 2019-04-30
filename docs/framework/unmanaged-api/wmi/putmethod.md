---
title: PutMethod 関数 (アンマネージ API リファレンス)
description: PutMethod 関数は、メソッドを作成します。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99bc65b0181a7c0ab7877273b3747ece91544f99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049259"
---
# <a name="putmethod-function"></a><span data-ttu-id="fe338-103">PutMethod 関数</span><span class="sxs-lookup"><span data-stu-id="fe338-103">PutMethod function</span></span>
<span data-ttu-id="fe338-104">メソッドが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fe338-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="fe338-105">構文</span><span class="sxs-lookup"><span data-stu-id="fe338-105">Syntax</span></span>  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="fe338-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe338-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="fe338-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="fe338-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="fe338-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="fe338-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="fe338-109">[in]作成するメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="fe338-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="fe338-110">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="fe338-110">[in] Reserved.</span></span> <span data-ttu-id="fe338-111">このパラメーターは、0 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe338-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="fe338-112">[in]コピーへのポインター、 [_parameters システム クラス](/windows/desktop/WmiSdk/--parameters)を格納している、`in`メソッドのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="fe338-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="fe338-113">場合、このパラメーターは無視されます設定`null`します。</span><span class="sxs-lookup"><span data-stu-id="fe338-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="fe338-114">[in] コピーへのポインター、 [_parameters システム クラス](/windows/desktop/WmiSdk/--parameters)を格納している、`out`メソッドのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="fe338-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="fe338-115">場合、このパラメーターは無視されます設定`null`します。</span><span class="sxs-lookup"><span data-stu-id="fe338-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="fe338-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="fe338-116">Return value</span></span>

<span data-ttu-id="fe338-117">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="fe338-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fe338-118">定数</span><span class="sxs-lookup"><span data-stu-id="fe338-118">Constant</span></span>  |<span data-ttu-id="fe338-119">値</span><span class="sxs-lookup"><span data-stu-id="fe338-119">Value</span></span>  |<span data-ttu-id="fe338-120">説明</span><span class="sxs-lookup"><span data-stu-id="fe338-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fe338-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="fe338-121">0x80041008</span></span> | <span data-ttu-id="fe338-122">1 つまたは複数のパラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="fe338-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="fe338-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="fe338-123">0x80041043</span></span> | <span data-ttu-id="fe338-124">`[in, out]`メソッド パラメーターの両方で指定された、 *pInSignature*と*pOutSignature*オブジェクトが別の修飾子を持ちます。</span><span class="sxs-lookup"><span data-stu-id="fe338-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="fe338-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="fe338-125">0x80041036</span></span> | <span data-ttu-id="fe338-126">メソッドのパラメーターでの指定が不足している、 **ID**修飾子。</span><span class="sxs-lookup"><span data-stu-id="fe338-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="fe338-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="fe338-127">0x80041038</span></span> | <span data-ttu-id="fe338-128">メソッドのパラメーターに割り当てられている ID のシリーズでは、連続がないか、0 から始まっていません。</span><span class="sxs-lookup"><span data-stu-id="fe338-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="fe338-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="fe338-129">0x80041039</span></span> | <span data-ttu-id="fe338-130">メソッドの戻り値が、 **ID**修飾子。</span><span class="sxs-lookup"><span data-stu-id="fe338-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="fe338-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="fe338-131">0x80041034</span></span> | <span data-ttu-id="fe338-132">親クラスから既存のメソッド名を再利用しようし、署名が一致しませんでした。</span><span class="sxs-lookup"><span data-stu-id="fe338-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="fe338-133">0</span><span class="sxs-lookup"><span data-stu-id="fe338-133">0</span></span> | <span data-ttu-id="fe338-134">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="fe338-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="fe338-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="fe338-135">Remarks</span></span>

<span data-ttu-id="fe338-136">この関数の呼び出しをラップする、 [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fe338-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="fe338-137">場合にのみ、このメソッドの呼び出しがサポート`ptr`CIM クラスの定義を示します。</span><span class="sxs-lookup"><span data-stu-id="fe338-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="fe338-138">メソッドの操作をからご利用いただけません[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) CIM インスタンスを指すポインター。</span><span class="sxs-lookup"><span data-stu-id="fe338-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="fe338-139">ユーザーは、アンダー スコアで開始または終了する名前を持つメソッドを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="fe338-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="fe338-140">これはシステム クラスとプロパティの予約されています。</span><span class="sxs-lookup"><span data-stu-id="fe338-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="fe338-141">メソッドで、`in`と`out`パラメーターはプロパティとして説明[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="fe338-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="fe338-142">`[in/out]`によって示される両方のオブジェクトへの同じプロパティを追加することでパラメーターを定義することができます、`pInSignature`と`pOutSignature`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="fe338-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="fe338-143">この場合、プロパティが同じ共有**ID**修飾子の値。</span><span class="sxs-lookup"><span data-stu-id="fe338-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="fe338-144">内の各プロパティを[_parameters](/windows/desktop/WmiSdk/--parameters)以外のオブジェクトをクラス`ReturnValue`必要があります、 **ID**修飾子、パラメーターの順序を表す 0 から始まる数値です。</span><span class="sxs-lookup"><span data-stu-id="fe338-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="fe338-145">ない 2 つのパラメーターがある同じ**ID**値、および no **ID**値をスキップすることができます。</span><span class="sxs-lookup"><span data-stu-id="fe338-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="fe338-146">いずれかの条件が発生した場合、`PutMethod`関数が返される`WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`します。</span><span class="sxs-lookup"><span data-stu-id="fe338-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="fe338-147">例</span><span class="sxs-lookup"><span data-stu-id="fe338-147">Example</span></span>

<span data-ttu-id="fe338-148">例については、次を参照してください。、 [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fe338-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="fe338-149">必要条件</span><span class="sxs-lookup"><span data-stu-id="fe338-149">Requirements</span></span>  
 <span data-ttu-id="fe338-150">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe338-150">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe338-151">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fe338-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fe338-152">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fe338-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe338-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe338-153">See also</span></span>

- [<span data-ttu-id="fe338-154">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="fe338-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

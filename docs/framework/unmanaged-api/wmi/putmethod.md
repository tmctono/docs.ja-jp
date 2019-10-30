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
ms.openlocfilehash: 1d409507de593cf198fe87340eece6820eaefc63
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127344"
---
# <a name="putmethod-function"></a><span data-ttu-id="739b4-103">PutMethod 関数</span><span class="sxs-lookup"><span data-stu-id="739b4-103">PutMethod function</span></span>
<span data-ttu-id="739b4-104">メソッドが作成されます。</span><span class="sxs-lookup"><span data-stu-id="739b4-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="739b4-105">構文</span><span class="sxs-lookup"><span data-stu-id="739b4-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="739b4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="739b4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="739b4-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="739b4-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="739b4-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="739b4-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="739b4-109">から作成するメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="739b4-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="739b4-110">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="739b4-110">[in] Reserved.</span></span> <span data-ttu-id="739b4-111">このパラメーターには0を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="739b4-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="739b4-112">からメソッドの `in` パラメーターを格納している、 [__ parameters システムクラス](/windows/desktop/WmiSdk/--parameters)のコピーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="739b4-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="739b4-113">`null`に設定した場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="739b4-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="739b4-114">から メソッドの `out` パラメーターを格納している、 [__ parameters システムクラス](/windows/desktop/WmiSdk/--parameters)のコピーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="739b4-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="739b4-115">`null`に設定した場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="739b4-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="739b4-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="739b4-116">Return value</span></span>

<span data-ttu-id="739b4-117">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="739b4-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="739b4-118">定数</span><span class="sxs-lookup"><span data-stu-id="739b4-118">Constant</span></span>  |<span data-ttu-id="739b4-119">[値]</span><span class="sxs-lookup"><span data-stu-id="739b4-119">Value</span></span>  |<span data-ttu-id="739b4-120">説明</span><span class="sxs-lookup"><span data-stu-id="739b4-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="739b4-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="739b4-121">0x80041008</span></span> | <span data-ttu-id="739b4-122">1つ以上のパラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="739b4-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="739b4-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="739b4-123">0x80041043</span></span> | <span data-ttu-id="739b4-124">*Pinsignature*オブジェクトと*poutsignature*オブジェクトの両方で指定された `[in, out]` method パラメーターの修飾子が異なります。</span><span class="sxs-lookup"><span data-stu-id="739b4-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="739b4-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="739b4-125">0x80041036</span></span> | <span data-ttu-id="739b4-126">メソッドパラメーターに**ID**修飾子の指定がありません。</span><span class="sxs-lookup"><span data-stu-id="739b4-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="739b4-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="739b4-127">0x80041038</span></span> | <span data-ttu-id="739b4-128">メソッドのパラメーターに割り当てられている ID 系列が連続していないか、0から始まっていません。</span><span class="sxs-lookup"><span data-stu-id="739b4-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="739b4-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="739b4-129">0x80041039</span></span> | <span data-ttu-id="739b4-130">メソッドの戻り値には**ID**修飾子があります。</span><span class="sxs-lookup"><span data-stu-id="739b4-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="739b4-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="739b4-131">0x80041034</span></span> | <span data-ttu-id="739b4-132">親クラスから既存のメソッド名を再利用しようとしましたが、シグネチャが一致しませんでした。</span><span class="sxs-lookup"><span data-stu-id="739b4-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="739b4-133">0</span><span class="sxs-lookup"><span data-stu-id="739b4-133">0</span></span> | <span data-ttu-id="739b4-134">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="739b4-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="739b4-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="739b4-135">Remarks</span></span>

<span data-ttu-id="739b4-136">この関数は、 [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="739b4-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="739b4-137">このメソッド呼び出しは、`ptr` が CIM クラス定義である場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="739b4-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="739b4-138">メソッド操作は、CIM インスタンスをポイントする[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)ポインターからは使用できません。</span><span class="sxs-lookup"><span data-stu-id="739b4-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="739b4-139">ユーザーは、アンダースコアで始まる名前または末尾を持つメソッドを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="739b4-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="739b4-140">これは、システムクラスおよびプロパティ用に予約されています。</span><span class="sxs-lookup"><span data-stu-id="739b4-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="739b4-141">メソッドの場合、`in` パラメーターと `out` パラメーターは[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)オブジェクトのプロパティとして記述されます。</span><span class="sxs-lookup"><span data-stu-id="739b4-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="739b4-142">`[in/out]` パラメーターを定義するには、`pInSignature` パラメーターと `pOutSignature` パラメーターが指す両方のオブジェクトに同じプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="739b4-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="739b4-143">この場合、プロパティは同じ**ID**修飾子値を共有します。</span><span class="sxs-lookup"><span data-stu-id="739b4-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="739b4-144">`ReturnValue` 以外の[__ Parameters](/windows/desktop/WmiSdk/--parameters)クラスオブジェクトの各プロパティには、パラメーターが表示される順序を識別する**ID**修飾子 (0 から始まる) が必要です。</span><span class="sxs-lookup"><span data-stu-id="739b4-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="739b4-145">2つのパラメーターの**id**値を同じにすることはできません。また、 **id**値をスキップすることもできません。</span><span class="sxs-lookup"><span data-stu-id="739b4-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="739b4-146">どちらかの条件が発生した場合、`PutMethod` 関数は `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`を返します。</span><span class="sxs-lookup"><span data-stu-id="739b4-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="739b4-147">例</span><span class="sxs-lookup"><span data-stu-id="739b4-147">Example</span></span>

<span data-ttu-id="739b4-148">例については、 [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)メソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="739b4-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="739b4-149">［要件］</span><span class="sxs-lookup"><span data-stu-id="739b4-149">Requirements</span></span>  
 <span data-ttu-id="739b4-150">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="739b4-150">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="739b4-151">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="739b4-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="739b4-152">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="739b4-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="739b4-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="739b4-153">See also</span></span>

- [<span data-ttu-id="739b4-154">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="739b4-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

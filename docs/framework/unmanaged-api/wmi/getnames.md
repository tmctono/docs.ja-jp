---
title: GetNames 関数 (アンマネージ API リファレンス)
description: GetNames 関数は、オブジェクトのプロパティの名前を取得します。
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 748767596a8f4680a2d7b63cb0579acaed5f53f8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798516"
---
# <a name="getnames-function"></a><span data-ttu-id="40aa8-103">GetNames 関数</span><span class="sxs-lookup"><span data-stu-id="40aa8-103">GetNames function</span></span>
<span data-ttu-id="40aa8-104">オブジェクトのプロパティの名前の一部またはすべてが取得されます。</span><span class="sxs-lookup"><span data-stu-id="40aa8-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="40aa8-105">構文</span><span class="sxs-lookup"><span data-stu-id="40aa8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="40aa8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40aa8-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="40aa8-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="40aa8-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="40aa8-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="40aa8-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="40aa8-109">からフィルターの一部とし`LPCWSTR`て動作する修飾子名を指定する、有効なへのポインター。</span><span class="sxs-lookup"><span data-stu-id="40aa8-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="40aa8-110">詳細については、「[解説](#remarks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40aa8-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="40aa8-111">このパラメーターは、`null` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="40aa8-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="40aa8-112">からビットフィールドの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="40aa8-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="40aa8-113">詳細については、「[解説](#remarks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40aa8-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="40aa8-114">からフィルター値に初期化さ`VARIANT`れた有効な構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="40aa8-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="40aa8-115">このパラメーターは、`null` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="40aa8-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="40aa8-116">入出力プロパティ名を格納している構造体。`SAFEARRAY`</span><span class="sxs-lookup"><span data-stu-id="40aa8-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="40aa8-117">エントリでは、このパラメーターは常にへ`null`のポインターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="40aa8-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="40aa8-118">詳細については、「[解説](#remarks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40aa8-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="40aa8-119">戻り値</span><span class="sxs-lookup"><span data-stu-id="40aa8-119">Return value</span></span>

<span data-ttu-id="40aa8-120">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="40aa8-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="40aa8-121">定数</span><span class="sxs-lookup"><span data-stu-id="40aa8-121">Constant</span></span>  |<span data-ttu-id="40aa8-122">Value</span><span class="sxs-lookup"><span data-stu-id="40aa8-122">Value</span></span>  |<span data-ttu-id="40aa8-123">説明</span><span class="sxs-lookup"><span data-stu-id="40aa8-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="40aa8-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="40aa8-124">0x80041001</span></span> | <span data-ttu-id="40aa8-125">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="40aa8-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="40aa8-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="40aa8-126">0x80041008</span></span> | <span data-ttu-id="40aa8-127">1つ以上のパラメーターが無効であるか、またはフラグとパラメーターの組み合わせが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="40aa8-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="40aa8-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="40aa8-128">0x80041006</span></span> | <span data-ttu-id="40aa8-129">操作を完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="40aa8-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="40aa8-130">0</span><span class="sxs-lookup"><span data-stu-id="40aa8-130">0</span></span> | <span data-ttu-id="40aa8-131">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="40aa8-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="40aa8-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="40aa8-132">Remarks</span></span>

<span data-ttu-id="40aa8-133">この関数は、 [IWbemClassObject:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="40aa8-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="40aa8-134">返される名前付きのは、フラグとパラメーターの組み合わせによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="40aa8-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="40aa8-135">たとえば、関数は、すべてのプロパティの名前、またはキープロパティの名前のみを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="40aa8-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="40aa8-136">プライマリフィルターは`lFlags`パラメーターで指定され、その他のパラメーターはそれに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="40aa8-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="40aa8-137">の`lFlags`フラグ値はビットフィールドです。</span><span class="sxs-lookup"><span data-stu-id="40aa8-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="40aa8-138">`lEnumFlags`引数として渡すことができるフラグは、 *WbemCli*ヘッダーファイルで定義されているビットフィールドです。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="40aa8-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="40aa8-139">各グループのフラグは、他のグループのフラグと組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="40aa8-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="40aa8-140">ただし、同じグループのフラグは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="40aa8-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="40aa8-141">グループ1フラグ</span><span class="sxs-lookup"><span data-stu-id="40aa8-141">Group 1 flags</span></span> |<span data-ttu-id="40aa8-142">値</span><span class="sxs-lookup"><span data-stu-id="40aa8-142">Value</span></span>  |<span data-ttu-id="40aa8-143">説明</span><span class="sxs-lookup"><span data-stu-id="40aa8-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="40aa8-144">0</span><span class="sxs-lookup"><span data-stu-id="40aa8-144">0</span></span> | <span data-ttu-id="40aa8-145">すべてのプロパティ名を返します。</span><span class="sxs-lookup"><span data-stu-id="40aa8-145">Return all property names.</span></span> <span data-ttu-id="40aa8-146">`strQualifierName`および`pQualifierVal`は使用されていません。</span><span class="sxs-lookup"><span data-stu-id="40aa8-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="40aa8-147">1</span><span class="sxs-lookup"><span data-stu-id="40aa8-147">1</span></span> | <span data-ttu-id="40aa8-148">`strQualifierName`パラメーターで指定された名前の修飾子を持つプロパティのみを返します。</span><span class="sxs-lookup"><span data-stu-id="40aa8-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="40aa8-149">このフラグを使用する場合は、を`strQualifierName`指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40aa8-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="40aa8-150">2</span><span class="sxs-lookup"><span data-stu-id="40aa8-150">2</span></span> |  <span data-ttu-id="40aa8-151">`strQualifierName`パラメーターで指定された名前の修飾子を持たないプロパティだけを返します。</span><span class="sxs-lookup"><span data-stu-id="40aa8-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="40aa8-152">このフラグを使用する場合は、を`strQualifierName`指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40aa8-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="40aa8-153">3</span><span class="sxs-lookup"><span data-stu-id="40aa8-153">3</span></span> | <span data-ttu-id="40aa8-154">`wszQualifierName`パラメーターで指定された名前の修飾子を持ち、 `pQualifierVal`構造体で指定された値と同じ値を持つプロパティのみを返します。</span><span class="sxs-lookup"><span data-stu-id="40aa8-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="40aa8-155">このフラグを使用する場合は、 `wszQualifierName`との`pQualifierValue`両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40aa8-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="40aa8-156">グループ2のフラグ</span><span class="sxs-lookup"><span data-stu-id="40aa8-156">Group 2 flags</span></span> |<span data-ttu-id="40aa8-157">値</span><span class="sxs-lookup"><span data-stu-id="40aa8-157">Value</span></span>  |<span data-ttu-id="40aa8-158">説明</span><span class="sxs-lookup"><span data-stu-id="40aa8-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="40aa8-159">0x4</span><span class="sxs-lookup"><span data-stu-id="40aa8-159">0x4</span></span> | <span data-ttu-id="40aa8-160">キーを定義するプロパティの名前のみを返します。</span><span class="sxs-lookup"><span data-stu-id="40aa8-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="40aa8-161">0x8</span><span class="sxs-lookup"><span data-stu-id="40aa8-161">0x8</span></span> | <span data-ttu-id="40aa8-162">オブジェクト参照であるプロパティ名だけを返します。</span><span class="sxs-lookup"><span data-stu-id="40aa8-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="40aa8-163">グループ3のフラグ</span><span class="sxs-lookup"><span data-stu-id="40aa8-163">Group 3 flags</span></span> |<span data-ttu-id="40aa8-164">値</span><span class="sxs-lookup"><span data-stu-id="40aa8-164">Value</span></span>  |<span data-ttu-id="40aa8-165">説明</span><span class="sxs-lookup"><span data-stu-id="40aa8-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="40aa8-166">0x10</span><span class="sxs-lookup"><span data-stu-id="40aa8-166">0x10</span></span> | <span data-ttu-id="40aa8-167">最派生クラスに属しているプロパティ名だけを返します。</span><span class="sxs-lookup"><span data-stu-id="40aa8-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="40aa8-168">親クラスからプロパティを除外します。</span><span class="sxs-lookup"><span data-stu-id="40aa8-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="40aa8-169">0x20</span><span class="sxs-lookup"><span data-stu-id="40aa8-169">0x20</span></span> | <span data-ttu-id="40aa8-170">親クラスに属するプロパティ名だけを返します。</span><span class="sxs-lookup"><span data-stu-id="40aa8-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="40aa8-171">0x30</span><span class="sxs-lookup"><span data-stu-id="40aa8-171">0x30</span></span> | <span data-ttu-id="40aa8-172">システムプロパティの名前のみを返します。</span><span class="sxs-lookup"><span data-stu-id="40aa8-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="40aa8-173">0x40</span><span class="sxs-lookup"><span data-stu-id="40aa8-173">0x40</span></span> | <span data-ttu-id="40aa8-174">システム以外のプロパティの名前のみを返します。</span><span class="sxs-lookup"><span data-stu-id="40aa8-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="40aa8-175">関数は、を返す`SAFEARRAY` `WBEM_S_NO_ERROR` `pstrNames`場合は常に新しいを割り当てます。この関数は常にを指すように設定されます。</span><span class="sxs-lookup"><span data-stu-id="40aa8-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="40aa8-176">指定したフィルターに一致するプロパティがない場合、返される配列には0個の要素を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="40aa8-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="40aa8-177">関数が以外`WBM_S_NO_ERROR`の値を返す場合、新しい`SAFEARRAY`構造体は返されません。</span><span class="sxs-lookup"><span data-stu-id="40aa8-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="40aa8-178">必要条件</span><span class="sxs-lookup"><span data-stu-id="40aa8-178">Requirements</span></span>  
 <span data-ttu-id="40aa8-179">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40aa8-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40aa8-180">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="40aa8-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="40aa8-181">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="40aa8-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40aa8-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="40aa8-182">See also</span></span>

- [<span data-ttu-id="40aa8-183">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="40aa8-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

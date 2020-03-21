---
title: 関数を取得します (アンマネージ API リファレンス)
description: 関数は、MOF 構文でオブジェクトのテキストレンダリングを返します。
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6881125760e0f1dc38e6b01917d5829edc95e3ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176787"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="d069b-103">GetObjectText 関数</span><span class="sxs-lookup"><span data-stu-id="d069b-103">GetObjectText function</span></span>
<span data-ttu-id="d069b-104">マネージ オブジェクト 形式 (MOF) 構文でオブジェクトのテキストレンダリングを返します。</span><span class="sxs-lookup"><span data-stu-id="d069b-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d069b-105">構文</span><span class="sxs-lookup"><span data-stu-id="d069b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a><span data-ttu-id="d069b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d069b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d069b-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="d069b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d069b-108">[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d069b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="d069b-109">[in]通常 0.</span><span class="sxs-lookup"><span data-stu-id="d069b-109">[in] Normally 0.</span></span> <span data-ttu-id="d069b-110">(`WBEM_FLAG_NO_FLAVORS`または 0x1) を指定すると、修飾子は伝搬情報やフレーバー情報なしで組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="d069b-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

<span data-ttu-id="d069b-111">`pstrObjectText`[アウト]`null`オン エントリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d069b-111">`pstrObjectText` [out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="d069b-112">戻り値の場合、オブジェクト`BSTR`の MOF 構文レンダリングを含む、新しく割り当てられたもの。</span><span class="sxs-lookup"><span data-stu-id="d069b-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="d069b-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="d069b-113">Return value</span></span>

<span data-ttu-id="d069b-114">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="d069b-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d069b-115">常時</span><span class="sxs-lookup"><span data-stu-id="d069b-115">Constant</span></span>  |<span data-ttu-id="d069b-116">Value</span><span class="sxs-lookup"><span data-stu-id="d069b-116">Value</span></span>  |<span data-ttu-id="d069b-117">説明</span><span class="sxs-lookup"><span data-stu-id="d069b-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="d069b-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="d069b-118">0x80041001</span></span> | <span data-ttu-id="d069b-119">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d069b-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d069b-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d069b-120">0x80041008</span></span> | <span data-ttu-id="d069b-121">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="d069b-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d069b-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d069b-122">0x80041006</span></span> | <span data-ttu-id="d069b-123">メモリ不足のため、操作を完了できません。</span><span class="sxs-lookup"><span data-stu-id="d069b-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d069b-124">0</span><span class="sxs-lookup"><span data-stu-id="d069b-124">0</span></span> | <span data-ttu-id="d069b-125">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="d069b-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="d069b-126">解説</span><span class="sxs-lookup"><span data-stu-id="d069b-126">Remarks</span></span>

<span data-ttu-id="d069b-127">この関数は、メソッドの呼び出し[を](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext)ラップします。</span><span class="sxs-lookup"><span data-stu-id="d069b-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="d069b-128">返される MOF テキストには、オブジェクトに関するすべての情報が含まれているわけではありませんが、MOF コンパイラが元のオブジェクトを再作成するのに十分な情報だけが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d069b-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="d069b-129">たとえば、伝達された修飾子や親クラスのプロパティは含まれません。</span><span class="sxs-lookup"><span data-stu-id="d069b-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="d069b-130">メソッドのパラメータのテキストを再構築するには、次のアルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="d069b-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="d069b-131">パラメーターは、ID 値の順序で再シーケンスされます。</span><span class="sxs-lookup"><span data-stu-id="d069b-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="d069b-132">として指定され`[in]`、1`[out]`つのパラメーターに結合されるパラメーター。</span><span class="sxs-lookup"><span data-stu-id="d069b-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>

<span data-ttu-id="d069b-133">`pstrObjectText`関数が呼び出されるとき`null`のポインタでなければなりません。ポインターの割り当て解除は行わないため、メソッド呼び出しの前に有効な文字列を指してはいけません。</span><span class="sxs-lookup"><span data-stu-id="d069b-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="d069b-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="d069b-134">Requirements</span></span>  
<span data-ttu-id="d069b-135">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d069b-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d069b-136">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d069b-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d069b-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d069b-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d069b-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="d069b-138">See also</span></span>

- [<span data-ttu-id="d069b-139">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d069b-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

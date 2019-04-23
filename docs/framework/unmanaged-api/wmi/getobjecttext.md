---
title: GetObjectText 関数 (アンマネージ API リファレンス)
description: GetObjectText 関数は、MOF 構文では、オブジェクトのテキストのレンダリングを返します。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d34cb399ac0e8780c442eeb2e95cebfd0a22ca02
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208320"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="1f9a4-103">GetObjectText 関数</span><span class="sxs-lookup"><span data-stu-id="1f9a4-103">GetObjectText function</span></span>
<span data-ttu-id="1f9a4-104">管理オブジェクト フォーマット (MOF) 構文では、オブジェクトのテキストのレンダリングを返します。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="1f9a4-105">構文</span><span class="sxs-lookup"><span data-stu-id="1f9a4-105">Syntax</span></span>  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="1f9a4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f9a4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1f9a4-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1f9a4-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="1f9a4-109">[in]通常は 0。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-109">[in] Normally 0.</span></span> <span data-ttu-id="1f9a4-110">場合`WBEM_FLAG_NO_FLAVORS`(または 0x1) 修飾子は、伝達またはフレーバーの情報も指定します。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="1f9a4-111">[out]ポインターを`null`エントリ。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="1f9a4-112">戻り時に、新しく割り当てられた`BSTR`がオブジェクトの MOF 構文のレンダリングを格納しています。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="1f9a4-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="1f9a4-113">Return value</span></span>

<span data-ttu-id="1f9a4-114">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1f9a4-115">定数</span><span class="sxs-lookup"><span data-stu-id="1f9a4-115">Constant</span></span>  |<span data-ttu-id="1f9a4-116">値</span><span class="sxs-lookup"><span data-stu-id="1f9a4-116">Value</span></span>  |<span data-ttu-id="1f9a4-117">説明</span><span class="sxs-lookup"><span data-stu-id="1f9a4-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="1f9a4-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="1f9a4-118">0x80041001</span></span> | <span data-ttu-id="1f9a4-119">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1f9a4-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1f9a4-120">0x80041008</span></span> | <span data-ttu-id="1f9a4-121">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1f9a4-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1f9a4-122">0x80041006</span></span> | <span data-ttu-id="1f9a4-123">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1f9a4-124">0</span><span class="sxs-lookup"><span data-stu-id="1f9a4-124">0</span></span> | <span data-ttu-id="1f9a4-125">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1f9a4-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="1f9a4-126">Remarks</span></span>

<span data-ttu-id="1f9a4-127">この関数の呼び出しをラップする、 [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext)メソッド。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="1f9a4-128">オブジェクトに関するすべての情報が、元のオブジェクトを再作成できる MOF コンパイラのための十分な情報のみ、返される MOF テキストは含まれません。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="1f9a4-129">たとえば、伝達された修飾子または親クラスのプロパティは含まれません。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="1f9a4-130">メソッドのパラメーターのテキストを再構築には、次のアルゴリズムが使用します。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="1f9a4-131">パラメーターは、その識別子の値の順序 resequenced されます。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="1f9a4-132">パラメーターとして指定されている`[in]`と`[out]`パラメーターを 1 つに結合されます。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
<span data-ttu-id="1f9a4-133">`pstrObjectText` ポインターである必要があります、`null`ポインターが解放されないため、メソッド呼び出しの前に有効な文字列をポイントする必要がありますいない、関数が呼び出されると;。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="1f9a4-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="1f9a4-134">Requirements</span></span>  
<span data-ttu-id="1f9a4-135">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f9a4-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f9a4-136">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1f9a4-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1f9a4-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1f9a4-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f9a4-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f9a4-138">See also</span></span>

- [<span data-ttu-id="1f9a4-139">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="1f9a4-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

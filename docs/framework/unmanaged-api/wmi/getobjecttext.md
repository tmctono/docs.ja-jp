---
title: GetObjectText 関数 (アンマネージ API リファレンス)
description: GetObjectText 関数は、MOF 構文でオブジェクトのテキスト形式のレンダリングを返します。
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
ms.openlocfilehash: d47fcd59204a4d114fc9f0dc5bc4550ba1681f33
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798508"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="e8d3e-103">GetObjectText 関数</span><span class="sxs-lookup"><span data-stu-id="e8d3e-103">GetObjectText function</span></span>
<span data-ttu-id="e8d3e-104">管理オブジェクトフォーマット (MOF) 構文におけるオブジェクトのテキスト形式のレンダリングを返します。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="e8d3e-105">構文</span><span class="sxs-lookup"><span data-stu-id="e8d3e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="e8d3e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e8d3e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e8d3e-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e8d3e-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="e8d3e-109">から通常は0です。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-109">[in] Normally 0.</span></span> <span data-ttu-id="e8d3e-110">( `WBEM_FLAG_NO_FLAVORS`または 0x1) が指定されている場合、修飾子は伝達またはフレーバー情報なしに含まれます。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="e8d3e-111">入出力`null` On エントリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="e8d3e-112">返されると、オブジェクトの`BSTR` MOF 構文レンダリングを含む新しく割り当てられた。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="e8d3e-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="e8d3e-113">Return value</span></span>

<span data-ttu-id="e8d3e-114">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e8d3e-115">定数</span><span class="sxs-lookup"><span data-stu-id="e8d3e-115">Constant</span></span>  |<span data-ttu-id="e8d3e-116">Value</span><span class="sxs-lookup"><span data-stu-id="e8d3e-116">Value</span></span>  |<span data-ttu-id="e8d3e-117">説明</span><span class="sxs-lookup"><span data-stu-id="e8d3e-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="e8d3e-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e8d3e-118">0x80041001</span></span> | <span data-ttu-id="e8d3e-119">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e8d3e-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e8d3e-120">0x80041008</span></span> | <span data-ttu-id="e8d3e-121">パラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e8d3e-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e8d3e-122">0x80041006</span></span> | <span data-ttu-id="e8d3e-123">操作を完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e8d3e-124">0</span><span class="sxs-lookup"><span data-stu-id="e8d3e-124">0</span></span> | <span data-ttu-id="e8d3e-125">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e8d3e-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="e8d3e-126">Remarks</span></span>

<span data-ttu-id="e8d3e-127">この関数は、 [IWbemClassObject:: GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="e8d3e-128">返される MOF テキストには、オブジェクトに関する情報がすべて含まれているわけではありませんが、MOF コンパイラが元のオブジェクトを再作成するのに十分な情報のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="e8d3e-129">たとえば、伝達された修飾子や親クラスのプロパティは含まれません。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="e8d3e-130">次のアルゴリズムは、メソッドのパラメーターのテキストを再構築するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="e8d3e-131">パラメーターは、識別子の値の順序で再シーケンスされます。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="e8d3e-132">`[in]` および`[out]`として指定されたパラメーターは、1つのパラメーターに結合されます。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
<span data-ttu-id="e8d3e-133">`pstrObjectText`は、関数が呼び出され`null`たときにへのポインターである必要があります。ポインターが割り当て解除されないため、メソッド呼び出しの前に有効な文字列を指すことはできません。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="e8d3e-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="e8d3e-134">Requirements</span></span>  
<span data-ttu-id="e8d3e-135">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8d3e-136">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="e8d3e-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e8d3e-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e8d3e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d3e-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8d3e-138">See also</span></span>

- [<span data-ttu-id="e8d3e-139">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e8d3e-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

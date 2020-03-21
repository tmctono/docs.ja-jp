---
title: 次のメソッド関数 (アンマネージ API リファレンス)
description: NextMethod 関数は、列挙型の次のメソッドを取得します。
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 36acd6135110a8865bd8efdda628c352c01b4f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174928"
---
# <a name="nextmethod-function"></a><span data-ttu-id="f5555-103">NextMethod 関数</span><span class="sxs-lookup"><span data-stu-id="f5555-103">NextMethod function</span></span>
<span data-ttu-id="f5555-104">[呼](beginmethodenumeration.md)び出しで始まる列挙体の次のメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="f5555-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f5555-105">構文</span><span class="sxs-lookup"><span data-stu-id="f5555-105">Syntax</span></span>  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```  

## <a name="parameters"></a><span data-ttu-id="f5555-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5555-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f5555-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="f5555-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f5555-108">[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f5555-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="f5555-109">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="f5555-109">[in] Reserved.</span></span> <span data-ttu-id="f5555-110">このパラメーターは 0 でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f5555-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="f5555-111">[アウト]呼び出しの`null`前を指すポインター。</span><span class="sxs-lookup"><span data-stu-id="f5555-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="f5555-112">関数が返されるときに、メソッド名を含む`BSTR`新しいアドレス。</span><span class="sxs-lookup"><span data-stu-id="f5555-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span>

`ppSignatureIn`  
<span data-ttu-id="f5555-113">[アウト]メソッドの`in`パラメーターを含む[IWbemClass オブジェクト](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインターを受け取るポインター。</span><span class="sxs-lookup"><span data-stu-id="f5555-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span>

`ppSignatureOut`  
<span data-ttu-id="f5555-114">[アウト]メソッドの`out`パラメーターを含む[IWbemClass オブジェクト](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインターを受け取るポインター。</span><span class="sxs-lookup"><span data-stu-id="f5555-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="f5555-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="f5555-115">Return value</span></span>

<span data-ttu-id="f5555-116">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="f5555-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f5555-117">常時</span><span class="sxs-lookup"><span data-stu-id="f5555-117">Constant</span></span>  |<span data-ttu-id="f5555-118">Value</span><span class="sxs-lookup"><span data-stu-id="f5555-118">Value</span></span>  |<span data-ttu-id="f5555-119">説明</span><span class="sxs-lookup"><span data-stu-id="f5555-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="f5555-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="f5555-120">0x8004101d</span></span> | <span data-ttu-id="f5555-121">[`BeginEnumeration`](beginenumeration.md)関数への呼び出しはありませんでした。</span><span class="sxs-lookup"><span data-stu-id="f5555-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f5555-122">0</span><span class="sxs-lookup"><span data-stu-id="f5555-122">0</span></span> | <span data-ttu-id="f5555-123">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="f5555-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="f5555-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="f5555-124">0x40005</span></span> | <span data-ttu-id="f5555-125">列挙体にこれ以上のプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="f5555-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="f5555-126">解説</span><span class="sxs-lookup"><span data-stu-id="f5555-126">Remarks</span></span>

<span data-ttu-id="f5555-127">この関数は、メソッドの呼び出しをラップ[します](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)。</span><span class="sxs-lookup"><span data-stu-id="f5555-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="f5555-128">呼び出し元は[、呼](beginmethodenumeration.md)び出すことによって列挙シーケンスを開始します。 `WBEM_S_NO_MORE_DATA`</span><span class="sxs-lookup"><span data-stu-id="f5555-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="f5555-129">必要に応じて、呼び出し元は[、呼](endmethodenumeration.md)び出しによってシーケンスを終了します。</span><span class="sxs-lookup"><span data-stu-id="f5555-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="f5555-130">呼び出し元は、いつでも呼び出すことによって、列挙[を](endmethodenumeration.md)早期に終了できます。</span><span class="sxs-lookup"><span data-stu-id="f5555-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="f5555-131">例</span><span class="sxs-lookup"><span data-stu-id="f5555-131">Example</span></span>

<span data-ttu-id="f5555-132">C++ の例については、メソッドを参照[してください](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)。</span><span class="sxs-lookup"><span data-stu-id="f5555-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f5555-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="f5555-133">Requirements</span></span>  
 <span data-ttu-id="f5555-134">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5555-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5555-135">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f5555-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f5555-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f5555-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5555-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5555-137">See also</span></span>

- [<span data-ttu-id="f5555-138">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f5555-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

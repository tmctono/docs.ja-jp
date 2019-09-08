---
title: NextMethod 関数 (アンマネージ API リファレンス)
description: NextMethod 関数は、列挙体の次のメソッドを取得します。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee743a4499824bea723043d5a2c7d57d7cbd7106
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798419"
---
# <a name="nextmethod-function"></a><span data-ttu-id="420e9-103">NextMethod 関数</span><span class="sxs-lookup"><span data-stu-id="420e9-103">NextMethod function</span></span>
<span data-ttu-id="420e9-104">[BeginMethodEnumeration](beginmethodenumeration.md)の呼び出しで始まる列挙体の次のメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="420e9-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="420e9-105">構文</span><span class="sxs-lookup"><span data-stu-id="420e9-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="420e9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="420e9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="420e9-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="420e9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="420e9-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="420e9-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="420e9-109">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="420e9-109">[in] Reserved.</span></span> <span data-ttu-id="420e9-110">このパラメーターには0を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="420e9-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="420e9-111">入出力呼び出しの前を`null`指すポインター。</span><span class="sxs-lookup"><span data-stu-id="420e9-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="420e9-112">関数から制御が戻るときに、メソッド名`BSTR`を含む新しいのアドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="420e9-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="420e9-113">入出力メソッドの`in`パラメーターを格納している[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインターを受け取るポインター。</span><span class="sxs-lookup"><span data-stu-id="420e9-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="420e9-114">入出力メソッドの`out`パラメーターを格納している[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインターを受け取るポインター。</span><span class="sxs-lookup"><span data-stu-id="420e9-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="420e9-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="420e9-115">Return value</span></span>

<span data-ttu-id="420e9-116">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="420e9-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="420e9-117">定数</span><span class="sxs-lookup"><span data-stu-id="420e9-117">Constant</span></span>  |<span data-ttu-id="420e9-118">Value</span><span class="sxs-lookup"><span data-stu-id="420e9-118">Value</span></span>  |<span data-ttu-id="420e9-119">説明</span><span class="sxs-lookup"><span data-stu-id="420e9-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="420e9-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="420e9-120">0x8004101d</span></span> | <span data-ttu-id="420e9-121">関数の[`BeginEnumeration`](beginenumeration.md)呼び出しがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="420e9-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="420e9-122">0</span><span class="sxs-lookup"><span data-stu-id="420e9-122">0</span></span> | <span data-ttu-id="420e9-123">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="420e9-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="420e9-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="420e9-124">0x40005</span></span> | <span data-ttu-id="420e9-125">列挙体にはそれ以上のプロパティがありません。</span><span class="sxs-lookup"><span data-stu-id="420e9-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="420e9-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="420e9-126">Remarks</span></span>

<span data-ttu-id="420e9-127">この関数は、 [IWbemClassObject:: nextmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="420e9-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="420e9-128">呼び出し元は、 [BeginMethodEnumeration](beginmethodenumeration.md)関数を呼び出すことによって列挙シーケンスを開始し、関数が戻る`WBEM_S_NO_MORE_DATA`まで [nextmethod] 関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="420e9-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="420e9-129">必要に応じて、呼び出し元は[EndMethodEnumeration](endmethodenumeration.md)を呼び出すことによってシーケンスを終了します。</span><span class="sxs-lookup"><span data-stu-id="420e9-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="420e9-130">呼び出し元は、いつでも[EndMethodEnumeration](endmethodenumeration.md)を呼び出すことによって、列挙を早期に終了する場合があります。</span><span class="sxs-lookup"><span data-stu-id="420e9-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="420e9-131">例</span><span class="sxs-lookup"><span data-stu-id="420e9-131">Example</span></span>

<span data-ttu-id="420e9-132">C++例については、 [IWbemClassObject:: nextmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)メソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="420e9-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="420e9-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="420e9-133">Requirements</span></span>  
 <span data-ttu-id="420e9-134">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="420e9-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="420e9-135">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="420e9-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="420e9-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="420e9-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="420e9-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="420e9-137">See also</span></span>

- [<span data-ttu-id="420e9-138">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="420e9-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

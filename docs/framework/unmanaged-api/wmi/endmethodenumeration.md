---
title: EndMethodEnumeration 関数 (アンマネージ API リファレンス)
description: EndMethodEnumeration 関数は、メソッドの列挙体シーケンスを終了します。
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 174cf76d4b0ddf07e67e02bff20a983dca08819a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132019"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="d74e9-103">EndMethodEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="d74e9-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="d74e9-104">[BeginMethodEnumeration 関数](beginmethodenumeration.md)の呼び出しで開始された列挙シーケンスを終了します。</span><span class="sxs-lookup"><span data-stu-id="d74e9-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="d74e9-105">構文</span><span class="sxs-lookup"><span data-stu-id="d74e9-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="d74e9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d74e9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d74e9-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="d74e9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d74e9-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d74e9-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="d74e9-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="d74e9-109">Return value</span></span>

<span data-ttu-id="d74e9-110">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="d74e9-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d74e9-111">定数</span><span class="sxs-lookup"><span data-stu-id="d74e9-111">Constant</span></span>  |<span data-ttu-id="d74e9-112">[値]</span><span class="sxs-lookup"><span data-stu-id="d74e9-112">Value</span></span>  |<span data-ttu-id="d74e9-113">説明</span><span class="sxs-lookup"><span data-stu-id="d74e9-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="d74e9-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="d74e9-114">0x8004101d</span></span> | <span data-ttu-id="d74e9-115">内部エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d74e9-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d74e9-116">0</span><span class="sxs-lookup"><span data-stu-id="d74e9-116">0</span></span> | <span data-ttu-id="d74e9-117">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="d74e9-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="d74e9-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="d74e9-118">Remarks</span></span>

<span data-ttu-id="d74e9-119">この関数は、 [IWbemClassObject:: EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="d74e9-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="d74e9-120">呼び出し元は、 [BeginMethodEnumeration 関数](beginmethodenumeration.md)を使用して列挙シーケンスを開始し、メソッドが `WBEM_S_NO_MORE_DATA`を返すまで[nextmethod 関数](nextmethod.md )を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d74e9-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="d74e9-121">呼び出し元は、必要に応じて `EndMethodEnumeration`を呼び出すことによってシーケンスを終了します。</span><span class="sxs-lookup"><span data-stu-id="d74e9-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="d74e9-122">呼び出し元は、いつでも `EndMethodEnumeration` を呼び出すことによって、列挙を早期に終了する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d74e9-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="d74e9-123">［要件］</span><span class="sxs-lookup"><span data-stu-id="d74e9-123">Requirements</span></span>  
 <span data-ttu-id="d74e9-124">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d74e9-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d74e9-125">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="d74e9-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d74e9-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d74e9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d74e9-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d74e9-127">See also</span></span>

- [<span data-ttu-id="d74e9-128">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d74e9-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

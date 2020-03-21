---
title: メソッド列挙関数 (アンマネージ API リファレンス)
description: 関数は、メソッド列挙体のシーケンスを終了します。
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
ms.openlocfilehash: 63667d0668f905ded2aedd961be0d1831faf838c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175006"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="3a426-103">EndMethodEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="3a426-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="3a426-104">関数の呼び出しで開始される列挙シーケンス[を](beginmethodenumeration.md)終了します。</span><span class="sxs-lookup"><span data-stu-id="3a426-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="3a426-105">構文</span><span class="sxs-lookup"><span data-stu-id="3a426-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="3a426-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a426-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3a426-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="3a426-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3a426-108">[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3a426-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="3a426-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="3a426-109">Return value</span></span>

<span data-ttu-id="3a426-110">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="3a426-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3a426-111">常時</span><span class="sxs-lookup"><span data-stu-id="3a426-111">Constant</span></span>  |<span data-ttu-id="3a426-112">Value</span><span class="sxs-lookup"><span data-stu-id="3a426-112">Value</span></span>  |<span data-ttu-id="3a426-113">説明</span><span class="sxs-lookup"><span data-stu-id="3a426-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="3a426-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="3a426-114">0x8004101d</span></span> | <span data-ttu-id="3a426-115">An internal error occurred.</span><span class="sxs-lookup"><span data-stu-id="3a426-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3a426-116">0</span><span class="sxs-lookup"><span data-stu-id="3a426-116">0</span></span> | <span data-ttu-id="3a426-117">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="3a426-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="3a426-118">解説</span><span class="sxs-lookup"><span data-stu-id="3a426-118">Remarks</span></span>

<span data-ttu-id="3a426-119">この関数は、メソッドの呼び出し[をラップします](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration)。</span><span class="sxs-lookup"><span data-stu-id="3a426-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="3a426-120">呼び出し元は[、BeginMethodEnumeration 関数](beginmethodenumeration.md)を使用して列挙シーケンスを開始し、メソッドが`WBEM_S_NO_MORE_DATA`返されるまで[NextMethod 関数](nextmethod.md )を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3a426-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="3a426-121">呼び出し元はオプションで、`EndMethodEnumeration`を呼び出してシーケンスを終了します。</span><span class="sxs-lookup"><span data-stu-id="3a426-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="3a426-122">呼び出し元は、いつでも呼`EndMethodEnumeration`び出すことによって、列挙を早期に終了できます。</span><span class="sxs-lookup"><span data-stu-id="3a426-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="3a426-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="3a426-123">Requirements</span></span>  
 <span data-ttu-id="3a426-124">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a426-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a426-125">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3a426-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3a426-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3a426-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a426-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a426-127">See also</span></span>

- [<span data-ttu-id="3a426-128">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3a426-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

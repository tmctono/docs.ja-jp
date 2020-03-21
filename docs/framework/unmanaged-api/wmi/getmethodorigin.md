---
title: 関数 (アンマネージ API リファレンス)
description: 関数は、メソッドが宣言されているクラスを決定します。
ms.date: 11/06/2017
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 5b4609b6649be875aea7dfcf52ba36b1e98ab7bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176800"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="4496d-103">GetMethodOrigin 関数</span><span class="sxs-lookup"><span data-stu-id="4496d-103">GetMethodOrigin function</span></span>
<span data-ttu-id="4496d-104">メソッドを宣言しているクラスが特定されます。</span><span class="sxs-lookup"><span data-stu-id="4496d-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="4496d-105">構文</span><span class="sxs-lookup"><span data-stu-id="4496d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```  

## <a name="parameters"></a><span data-ttu-id="4496d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4496d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4496d-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="4496d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4496d-108">[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4496d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="4496d-109">[in]所有クラスが要求されているオブジェクトのメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="4496d-109">[in] The name of the method for the object whose owning class is being requested.</span></span>

`pstrClassName`  
<span data-ttu-id="4496d-110">[アウト]メソッドを所有するクラスの名前を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4496d-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="4496d-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="4496d-111">Return value</span></span>

<span data-ttu-id="4496d-112">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="4496d-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4496d-113">常時</span><span class="sxs-lookup"><span data-stu-id="4496d-113">Constant</span></span>  |<span data-ttu-id="4496d-114">Value</span><span class="sxs-lookup"><span data-stu-id="4496d-114">Value</span></span>  |<span data-ttu-id="4496d-115">説明</span><span class="sxs-lookup"><span data-stu-id="4496d-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="4496d-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="4496d-116">0x80041002</span></span> | <span data-ttu-id="4496d-117">指定されたメソッドが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="4496d-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4496d-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4496d-118">0x80041008</span></span> | <span data-ttu-id="4496d-119">1 つ以上のパラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="4496d-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4496d-120">0</span><span class="sxs-lookup"><span data-stu-id="4496d-120">0</span></span> | <span data-ttu-id="4496d-121">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="4496d-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4496d-122">解説</span><span class="sxs-lookup"><span data-stu-id="4496d-122">Remarks</span></span>

<span data-ttu-id="4496d-123">この関数は、メソッドの呼び出し[を](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)ラップします。</span><span class="sxs-lookup"><span data-stu-id="4496d-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="4496d-124">クラスは 1 つ以上の基本クラスからメソッドを継承できるため、開発者は、特定のメソッドが定義されているクラスを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4496d-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="4496d-125">この`pstrClassName`パラメーターはパラメーターであるため、関数が`BSTR`呼び出される前にパラメーターが有効`out`であることを指してはなりません。このポインターは、関数が戻った後に割り当て解除されません。</span><span class="sxs-lookup"><span data-stu-id="4496d-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="4496d-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="4496d-126">Requirements</span></span>  
<span data-ttu-id="4496d-127">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4496d-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4496d-128">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4496d-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4496d-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4496d-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4496d-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="4496d-130">See also</span></span>

- [<span data-ttu-id="4496d-131">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="4496d-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

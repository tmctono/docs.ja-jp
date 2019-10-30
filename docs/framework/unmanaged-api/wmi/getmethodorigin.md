---
title: GetMethodOrigin 関数 (アンマネージ API リファレンス)
description: GetMethodOrigin 関数は、メソッドが宣言されているクラスを特定します。
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
ms.openlocfilehash: 1f669d5721a7bd9434f0ce4b1e2290c0633e1b46
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102538"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="5efab-103">GetMethodOrigin 関数</span><span class="sxs-lookup"><span data-stu-id="5efab-103">GetMethodOrigin function</span></span>
<span data-ttu-id="5efab-104">メソッドを宣言しているクラスが特定されます。</span><span class="sxs-lookup"><span data-stu-id="5efab-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="5efab-105">構文</span><span class="sxs-lookup"><span data-stu-id="5efab-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="5efab-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5efab-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5efab-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="5efab-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5efab-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5efab-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="5efab-109">から所有クラスが要求されているオブジェクトのメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="5efab-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="5efab-110">入出力メソッドを所有するクラスの名前を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5efab-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="5efab-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="5efab-111">Return value</span></span>

<span data-ttu-id="5efab-112">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="5efab-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5efab-113">定数</span><span class="sxs-lookup"><span data-stu-id="5efab-113">Constant</span></span>  |<span data-ttu-id="5efab-114">[値]</span><span class="sxs-lookup"><span data-stu-id="5efab-114">Value</span></span>  |<span data-ttu-id="5efab-115">説明</span><span class="sxs-lookup"><span data-stu-id="5efab-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="5efab-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="5efab-116">0x80041002</span></span> | <span data-ttu-id="5efab-117">指定されたメソッドが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="5efab-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5efab-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5efab-118">0x80041008</span></span> | <span data-ttu-id="5efab-119">1つ以上のパラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="5efab-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5efab-120">0</span><span class="sxs-lookup"><span data-stu-id="5efab-120">0</span></span> | <span data-ttu-id="5efab-121">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="5efab-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5efab-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="5efab-122">Remarks</span></span>

<span data-ttu-id="5efab-123">この関数は、 [IWbemClassObject:: GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="5efab-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="5efab-124">クラスは1つまたは複数の基底クラスからメソッドを継承できるため、多くの場合、開発者は特定のメソッドが定義されているクラスを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5efab-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="5efab-125">`pstrClassName` パラメーターは `out` パラメーターであるため、関数が呼び出される前に、有効な `BSTR` をポイントすることはできません。関数から制御が戻った後、このポインターの割り当ては解除されません。</span><span class="sxs-lookup"><span data-stu-id="5efab-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="5efab-126">［要件］</span><span class="sxs-lookup"><span data-stu-id="5efab-126">Requirements</span></span>  
<span data-ttu-id="5efab-127">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5efab-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5efab-128">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="5efab-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5efab-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5efab-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5efab-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="5efab-130">See also</span></span>

- [<span data-ttu-id="5efab-131">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="5efab-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

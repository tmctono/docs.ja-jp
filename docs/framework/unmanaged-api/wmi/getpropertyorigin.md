---
title: GetPropertyOrigin 関数 (アンマネージ API リファレンス)
description: GetPropertyOrigin 関数は、プロパティが宣言されているクラスを決定します。
ms.date: 11/06/2017
api_name:
- GetPropertyOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyOrigin
helpviewer_keywords:
- GetPropertyOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 542c4a01a9fd56587d51421709ffb990707f2ae0
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636792"
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="fea76-103">GetPropertyOrigin 関数</span><span class="sxs-lookup"><span data-stu-id="fea76-103">GetPropertyOrigin function</span></span>

<span data-ttu-id="fea76-104">プロパティを宣言しているクラスが特定されます。</span><span class="sxs-lookup"><span data-stu-id="fea76-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="fea76-105">構文</span><span class="sxs-lookup"><span data-stu-id="fea76-105">Syntax</span></span>

```cpp
HRESULT GetPropertyOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```

## <a name="parameters"></a><span data-ttu-id="fea76-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fea76-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="fea76-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="fea76-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="fea76-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="fea76-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`\
<span data-ttu-id="fea76-109">[in]所有するクラスが要求されているオブジェクトのプロパティの名前。</span><span class="sxs-lookup"><span data-stu-id="fea76-109">[in] The name of the property for the object whose owning class is being requested.</span></span>

`pstrClassName`\
<span data-ttu-id="fea76-110">[out]プロパティを所有するクラスの名前を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="fea76-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="fea76-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="fea76-111">Return value</span></span>

<span data-ttu-id="fea76-112">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="fea76-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fea76-113">定数</span><span class="sxs-lookup"><span data-stu-id="fea76-113">Constant</span></span>  |<span data-ttu-id="fea76-114">値</span><span class="sxs-lookup"><span data-stu-id="fea76-114">Value</span></span>  |<span data-ttu-id="fea76-115">説明</span><span class="sxs-lookup"><span data-stu-id="fea76-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="fea76-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="fea76-116">0x80041001</span></span> | <span data-ttu-id="fea76-117">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fea76-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="fea76-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="fea76-118">0x80041002</span></span> | <span data-ttu-id="fea76-119">指定したプロパティが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="fea76-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fea76-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="fea76-120">0x80041008</span></span> | <span data-ttu-id="fea76-121">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="fea76-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="fea76-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="fea76-122">0x80041006</span></span> | <span data-ttu-id="fea76-123">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="fea76-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="fea76-124">0</span><span class="sxs-lookup"><span data-stu-id="fea76-124">0</span></span> | <span data-ttu-id="fea76-125">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="fea76-125">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="fea76-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="fea76-126">Remarks</span></span>

<span data-ttu-id="fea76-127">この関数の呼び出しをラップする、 [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin)メソッド。</span><span class="sxs-lookup"><span data-stu-id="fea76-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) method.</span></span>

<span data-ttu-id="fea76-128">クラスは、1 つまたは複数の基底クラスからプロパティを継承することができます、ため開発者は多くの場合に指定されたメソッドが定義されているプロパティを確認するとします。</span><span class="sxs-lookup"><span data-stu-id="fea76-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="fea76-129">`pstrClassName`パラメーターが有効なをポイントする必要がありますいない`BSTR`ため、これは、関数が呼び出される前に、`out`パラメーター。 この関数によって返された後に、ポインターが割り当て解除されません。</span><span class="sxs-lookup"><span data-stu-id="fea76-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="fea76-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="fea76-130">Requirements</span></span>

<span data-ttu-id="fea76-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fea76-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="fea76-132">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fea76-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="fea76-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fea76-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="fea76-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="fea76-134">See also</span></span>

- [<span data-ttu-id="fea76-135">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="fea76-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

---
title: GetPropertyQualifierSet 関数 (アンマネージ API リファレンス)
description: GetPropertyQualifierSet 関数は、プロパティに設定されている修飾子を取得します。
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7bce241d10051e4c6be94cdfa40de23773fb0bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798473"
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="92bda-103">GetPropertyQualifierSet 関数</span><span class="sxs-lookup"><span data-stu-id="92bda-103">GetPropertyQualifierSet function</span></span>

<span data-ttu-id="92bda-104">特定のプロパティで設定された修飾子が取得されます。</span><span class="sxs-lookup"><span data-stu-id="92bda-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="92bda-105">構文</span><span class="sxs-lookup"><span data-stu-id="92bda-105">Syntax</span></span>

```cpp
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="92bda-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="92bda-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="92bda-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="92bda-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="92bda-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="92bda-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="92bda-109">からプロパティ名。</span><span class="sxs-lookup"><span data-stu-id="92bda-109">[in] The property  name.</span></span> <span data-ttu-id="92bda-110">`wszProperty`は有効`LPCWSTR`なを指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="92bda-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="92bda-111">入出力プロパティの修飾子へのアクセスを許可するインターフェイスポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="92bda-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="92bda-112">`ppQualSet` として `null` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="92bda-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="92bda-113">エラーが発生した場合、新しいオブジェクトは返されず、ポインターはを`null`指すように設定されます。</span><span class="sxs-lookup"><span data-stu-id="92bda-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="92bda-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="92bda-114">Return value</span></span>

<span data-ttu-id="92bda-115">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="92bda-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="92bda-116">定数</span><span class="sxs-lookup"><span data-stu-id="92bda-116">Constant</span></span>  |<span data-ttu-id="92bda-117">Value</span><span class="sxs-lookup"><span data-stu-id="92bda-117">Value</span></span>  |<span data-ttu-id="92bda-118">説明</span><span class="sxs-lookup"><span data-stu-id="92bda-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="92bda-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="92bda-119">0x80041001</span></span> | <span data-ttu-id="92bda-120">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="92bda-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="92bda-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="92bda-121">0x80041002</span></span> | <span data-ttu-id="92bda-122">指定されたメソッドは存在しません。</span><span class="sxs-lookup"><span data-stu-id="92bda-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="92bda-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="92bda-123">0x80041006</span></span> | <span data-ttu-id="92bda-124">操作を完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="92bda-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="92bda-125">0x80041008</span><span class="sxs-lookup"><span data-stu-id="92bda-125">0x80041008</span></span> | <span data-ttu-id="92bda-126">パラメーターが`null`です。</span><span class="sxs-lookup"><span data-stu-id="92bda-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="92bda-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="92bda-127">0x80041030</span></span> | <span data-ttu-id="92bda-128">関数は、システムプロパティの修飾子を取得しようとします。</span><span class="sxs-lookup"><span data-stu-id="92bda-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="92bda-129">0</span><span class="sxs-lookup"><span data-stu-id="92bda-129">0</span></span> | <span data-ttu-id="92bda-130">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="92bda-130">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="92bda-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="92bda-131">Remarks</span></span>

<span data-ttu-id="92bda-132">この関数は、 [IWbemClassObject:: GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="92bda-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) method.</span></span>

<span data-ttu-id="92bda-133">この関数の呼び出しは、現在のオブジェクトが CIM クラス定義である場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="92bda-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="92bda-134">CIM インスタンスを指す[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)ポインターでは、メソッド操作は使用できません。</span><span class="sxs-lookup"><span data-stu-id="92bda-134">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="92bda-135">各メソッドは独自の修飾子を持つことができるため、 [IWbemQualifierSet ポインター](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)によって呼び出し元はこれらの修飾子を追加、編集、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="92bda-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="92bda-136">システムプロパティに修飾子がないため、システムプロパティ`WBEM_E_SYSTEM_PROPERTY`の[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)ポインターを取得しようとすると、関数はを返します。</span><span class="sxs-lookup"><span data-stu-id="92bda-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="92bda-137">必要条件</span><span class="sxs-lookup"><span data-stu-id="92bda-137">Requirements</span></span>

<span data-ttu-id="92bda-138">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92bda-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="92bda-139">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="92bda-139">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="92bda-140">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="92bda-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="92bda-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="92bda-141">See also</span></span>

- [<span data-ttu-id="92bda-142">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="92bda-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

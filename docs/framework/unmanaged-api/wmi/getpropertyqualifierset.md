---
title: GetPropertyQualifierSet 関数 (アンマネージ API リファレンス)
description: GetPropertyQualifierSet 関数は、プロパティの設定、修飾子を取得します。
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
ms.openlocfilehash: cdb9f748279e4e74c0dbd1ced1f48e3a24b9904d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61959537"
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="3439a-103">GetPropertyQualifierSet 関数</span><span class="sxs-lookup"><span data-stu-id="3439a-103">GetPropertyQualifierSet function</span></span>

<span data-ttu-id="3439a-104">特定のプロパティで設定された修飾子が取得されます。</span><span class="sxs-lookup"><span data-stu-id="3439a-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="3439a-105">構文</span><span class="sxs-lookup"><span data-stu-id="3439a-105">Syntax</span></span>

```cpp
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="3439a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3439a-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="3439a-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="3439a-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="3439a-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="3439a-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="3439a-109">[in]プロパティ名。</span><span class="sxs-lookup"><span data-stu-id="3439a-109">[in] The property  name.</span></span> <span data-ttu-id="3439a-110">`wszProperty` 有効なをポイントする必要があります`LPCWSTR`します。</span><span class="sxs-lookup"><span data-stu-id="3439a-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="3439a-111">[out]プロパティの修飾子にアクセスできるインターフェイス ポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3439a-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="3439a-112">`ppQualSet` として `null` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3439a-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="3439a-113">かどうかは、エラーが発生し、新しいオブジェクトは返されませんを指すポインターを設定`null`します。</span><span class="sxs-lookup"><span data-stu-id="3439a-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="3439a-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="3439a-114">Return value</span></span>

<span data-ttu-id="3439a-115">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="3439a-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3439a-116">定数</span><span class="sxs-lookup"><span data-stu-id="3439a-116">Constant</span></span>  |<span data-ttu-id="3439a-117">値</span><span class="sxs-lookup"><span data-stu-id="3439a-117">Value</span></span>  |<span data-ttu-id="3439a-118">説明</span><span class="sxs-lookup"><span data-stu-id="3439a-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="3439a-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="3439a-119">0x80041001</span></span> | <span data-ttu-id="3439a-120">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3439a-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="3439a-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="3439a-121">0x80041002</span></span> | <span data-ttu-id="3439a-122">指定されたメソッドが存在しません。</span><span class="sxs-lookup"><span data-stu-id="3439a-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="3439a-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="3439a-123">0x80041006</span></span> | <span data-ttu-id="3439a-124">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="3439a-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3439a-125">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3439a-125">0x80041008</span></span> | <span data-ttu-id="3439a-126">パラメーターが`null`します。</span><span class="sxs-lookup"><span data-stu-id="3439a-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="3439a-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="3439a-127">0x80041030</span></span> | <span data-ttu-id="3439a-128">関数は、システム プロパティの修飾子を取得しようとします。</span><span class="sxs-lookup"><span data-stu-id="3439a-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3439a-129">0</span><span class="sxs-lookup"><span data-stu-id="3439a-129">0</span></span> | <span data-ttu-id="3439a-130">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="3439a-130">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="3439a-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="3439a-131">Remarks</span></span>

<span data-ttu-id="3439a-132">この関数の呼び出しをラップする、 [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset)メソッド。</span><span class="sxs-lookup"><span data-stu-id="3439a-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) method.</span></span>

<span data-ttu-id="3439a-133">この関数の呼び出しがサポートされるは、現在のオブジェクトが CIM クラスの定義である場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="3439a-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="3439a-134">メソッドの操作は利用できません[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) CIM インスタンスを指すポインター。</span><span class="sxs-lookup"><span data-stu-id="3439a-134">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="3439a-135">各メソッドには、独自の修飾子が可能性があるため、 [IWbemQualifierSet ポインター](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)により、呼び出し元を追加、編集、またはこれらの修飾子を削除します。</span><span class="sxs-lookup"><span data-stu-id="3439a-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="3439a-136">システムのプロパティは修飾子を持たないため、関数を返します`WBEM_E_SYSTEM_PROPERTY`を取得しようとした場合、 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)システム プロパティへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3439a-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="3439a-137">必要条件</span><span class="sxs-lookup"><span data-stu-id="3439a-137">Requirements</span></span>

<span data-ttu-id="3439a-138">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3439a-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="3439a-139">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3439a-139">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="3439a-140">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3439a-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3439a-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="3439a-141">See also</span></span>

- [<span data-ttu-id="3439a-142">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3439a-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
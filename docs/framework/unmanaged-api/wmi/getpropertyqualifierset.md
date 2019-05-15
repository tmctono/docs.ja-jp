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
ms.openlocfilehash: 588c56c80cc55df3689178875a9a0500cd0ca7b8
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636397"
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="e5fc2-103">GetPropertyQualifierSet 関数</span><span class="sxs-lookup"><span data-stu-id="e5fc2-103">GetPropertyQualifierSet function</span></span>

<span data-ttu-id="e5fc2-104">特定のプロパティで設定された修飾子が取得されます。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e5fc2-105">構文</span><span class="sxs-lookup"><span data-stu-id="e5fc2-105">Syntax</span></span>

```cpp
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="e5fc2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e5fc2-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="e5fc2-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="e5fc2-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="e5fc2-109">[in]プロパティ名。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-109">[in] The property  name.</span></span> <span data-ttu-id="e5fc2-110">`wszProperty` 有効なをポイントする必要があります`LPCWSTR`します。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="e5fc2-111">[out]プロパティの修飾子にアクセスできるインターフェイス ポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="e5fc2-112">`ppQualSet` として `null` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="e5fc2-113">かどうかは、エラーが発生し、新しいオブジェクトは返されませんを指すポインターを設定`null`します。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="e5fc2-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="e5fc2-114">Return value</span></span>

<span data-ttu-id="e5fc2-115">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e5fc2-116">定数</span><span class="sxs-lookup"><span data-stu-id="e5fc2-116">Constant</span></span>  |<span data-ttu-id="e5fc2-117">値</span><span class="sxs-lookup"><span data-stu-id="e5fc2-117">Value</span></span>  |<span data-ttu-id="e5fc2-118">説明</span><span class="sxs-lookup"><span data-stu-id="e5fc2-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="e5fc2-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e5fc2-119">0x80041001</span></span> | <span data-ttu-id="e5fc2-120">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="e5fc2-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e5fc2-121">0x80041002</span></span> | <span data-ttu-id="e5fc2-122">指定されたメソッドが存在しません。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e5fc2-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e5fc2-123">0x80041006</span></span> | <span data-ttu-id="e5fc2-124">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e5fc2-125">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e5fc2-125">0x80041008</span></span> | <span data-ttu-id="e5fc2-126">パラメーターが`null`します。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="e5fc2-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="e5fc2-127">0x80041030</span></span> | <span data-ttu-id="e5fc2-128">関数は、システム プロパティの修飾子を取得しようとします。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e5fc2-129">0</span><span class="sxs-lookup"><span data-stu-id="e5fc2-129">0</span></span> | <span data-ttu-id="e5fc2-130">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-130">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="e5fc2-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5fc2-131">Remarks</span></span>

<span data-ttu-id="e5fc2-132">この関数の呼び出しをラップする、 [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset)メソッド。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) method.</span></span>

<span data-ttu-id="e5fc2-133">この関数の呼び出しがサポートされるは、現在のオブジェクトが CIM クラスの定義である場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="e5fc2-134">メソッドの操作は利用できません[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) CIM インスタンスを指すポインター。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-134">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="e5fc2-135">各メソッドには、独自の修飾子が可能性があるため、 [IWbemQualifierSet ポインター](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)により、呼び出し元を追加、編集、またはこれらの修飾子を削除します。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="e5fc2-136">システムのプロパティは修飾子を持たないため、関数を返します`WBEM_E_SYSTEM_PROPERTY`を取得しようとした場合、 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)システム プロパティへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="e5fc2-137">必要条件</span><span class="sxs-lookup"><span data-stu-id="e5fc2-137">Requirements</span></span>

<span data-ttu-id="e5fc2-138">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5fc2-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="e5fc2-139">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e5fc2-139">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="e5fc2-140">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e5fc2-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e5fc2-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5fc2-141">See also</span></span>

- [<span data-ttu-id="e5fc2-142">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e5fc2-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

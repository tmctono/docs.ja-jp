---
title: GetMethodQualifierSet 関数 (アンマネージ API リファレンス)
description: GetMethodQualifierSet 関数は、メソッドの修飾子のセットを取得します。
ms.date: 11/06/2017
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9257ba57e0d087e3d6b9c7bb995b49a6b814c5f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040743"
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="c4b44-103">GetMethodQualifierSet 関数</span><span class="sxs-lookup"><span data-stu-id="c4b44-103">GetMethodQualifierSet function</span></span>

<span data-ttu-id="c4b44-104">特定のメソッドで設定された修飾子が取得されます。</span><span class="sxs-lookup"><span data-stu-id="c4b44-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="c4b44-105">構文</span><span class="sxs-lookup"><span data-stu-id="c4b44-105">Syntax</span></span>

```cpp
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="c4b44-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c4b44-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="c4b44-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="c4b44-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="c4b44-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="c4b44-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="c4b44-109">[in]メソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="c4b44-109">[in] The method  name.</span></span> <span data-ttu-id="c4b44-110">`wszMethod` 有効なをポイントする必要があります`LPCWSTR`します。</span><span class="sxs-lookup"><span data-stu-id="c4b44-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="c4b44-111">[out]メソッドの修飾子にアクセスできるインターフェイス ポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c4b44-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="c4b44-112">`ppQualSet` として `null` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4b44-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="c4b44-113">かどうかは、エラーが発生し、新しいオブジェクトは返されませんを指すポインターを設定`null`します。</span><span class="sxs-lookup"><span data-stu-id="c4b44-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="c4b44-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="c4b44-114">Return value</span></span>

<span data-ttu-id="c4b44-115">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="c4b44-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c4b44-116">定数</span><span class="sxs-lookup"><span data-stu-id="c4b44-116">Constant</span></span>  |<span data-ttu-id="c4b44-117">値</span><span class="sxs-lookup"><span data-stu-id="c4b44-117">Value</span></span>  |<span data-ttu-id="c4b44-118">説明</span><span class="sxs-lookup"><span data-stu-id="c4b44-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="c4b44-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="c4b44-119">0x80041002</span></span> | <span data-ttu-id="c4b44-120">指定されたメソッドが存在しません。</span><span class="sxs-lookup"><span data-stu-id="c4b44-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c4b44-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c4b44-121">0x80041008</span></span> | <span data-ttu-id="c4b44-122">パラメーターが`null`します。</span><span class="sxs-lookup"><span data-stu-id="c4b44-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c4b44-123">0</span><span class="sxs-lookup"><span data-stu-id="c4b44-123">0</span></span> | <span data-ttu-id="c4b44-124">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="c4b44-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="c4b44-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="c4b44-125">Remarks</span></span>

<span data-ttu-id="c4b44-126">この関数の呼び出しをラップする、 [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset)メソッド。</span><span class="sxs-lookup"><span data-stu-id="c4b44-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) method.</span></span>

<span data-ttu-id="c4b44-127">この関数の呼び出しがサポートされるは、現在のオブジェクトが CIM クラスの定義である場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="c4b44-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="c4b44-128">メソッドの操作は利用できません[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) CIM インスタンスを指すポインター。</span><span class="sxs-lookup"><span data-stu-id="c4b44-128">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="c4b44-129">各メソッドには、独自の修飾子が可能性があるため、 [IWbemQualifierSet ポインター](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)により、呼び出し元を追加、編集、またはこれらの修飾子を削除します。</span><span class="sxs-lookup"><span data-stu-id="c4b44-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="c4b44-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="c4b44-130">Requirements</span></span>

<span data-ttu-id="c4b44-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4b44-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="c4b44-132">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c4b44-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="c4b44-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c4b44-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c4b44-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4b44-134">See also</span></span>

- [<span data-ttu-id="c4b44-135">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c4b44-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
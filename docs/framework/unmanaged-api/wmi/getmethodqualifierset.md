---
title: GetMethodQualifierSet 関数 (アンマネージ API リファレンス)
description: GetMethodQualifierSet 関数は、メソッドの修飾子セットを取得します。
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
ms.openlocfilehash: 86a7788736c3c12cfcfd405de88dfadfb14c1eca
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798531"
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="485b2-103">GetMethodQualifierSet 関数</span><span class="sxs-lookup"><span data-stu-id="485b2-103">GetMethodQualifierSet function</span></span>

<span data-ttu-id="485b2-104">特定のメソッドで設定された修飾子が取得されます。</span><span class="sxs-lookup"><span data-stu-id="485b2-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="485b2-105">構文</span><span class="sxs-lookup"><span data-stu-id="485b2-105">Syntax</span></span>

```cpp
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="485b2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="485b2-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="485b2-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="485b2-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="485b2-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="485b2-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="485b2-109">からメソッド名。</span><span class="sxs-lookup"><span data-stu-id="485b2-109">[in] The method  name.</span></span> <span data-ttu-id="485b2-110">`wszMethod`は有効`LPCWSTR`なを指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="485b2-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="485b2-111">入出力メソッドの修飾子へのアクセスを許可するインターフェイスポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="485b2-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="485b2-112">`ppQualSet` として `null` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="485b2-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="485b2-113">エラーが発生した場合、新しいオブジェクトは返されず、ポインターはを`null`指すように設定されます。</span><span class="sxs-lookup"><span data-stu-id="485b2-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="485b2-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="485b2-114">Return value</span></span>

<span data-ttu-id="485b2-115">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="485b2-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="485b2-116">定数</span><span class="sxs-lookup"><span data-stu-id="485b2-116">Constant</span></span>  |<span data-ttu-id="485b2-117">Value</span><span class="sxs-lookup"><span data-stu-id="485b2-117">Value</span></span>  |<span data-ttu-id="485b2-118">説明</span><span class="sxs-lookup"><span data-stu-id="485b2-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="485b2-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="485b2-119">0x80041002</span></span> | <span data-ttu-id="485b2-120">指定されたメソッドは存在しません。</span><span class="sxs-lookup"><span data-stu-id="485b2-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="485b2-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="485b2-121">0x80041008</span></span> | <span data-ttu-id="485b2-122">パラメーターが`null`です。</span><span class="sxs-lookup"><span data-stu-id="485b2-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="485b2-123">0</span><span class="sxs-lookup"><span data-stu-id="485b2-123">0</span></span> | <span data-ttu-id="485b2-124">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="485b2-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="485b2-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="485b2-125">Remarks</span></span>

<span data-ttu-id="485b2-126">この関数は、 [IWbemClassObject:: GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="485b2-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) method.</span></span>

<span data-ttu-id="485b2-127">この関数の呼び出しは、現在のオブジェクトが CIM クラス定義である場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="485b2-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="485b2-128">CIM インスタンスを指す[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)ポインターでは、メソッド操作は使用できません。</span><span class="sxs-lookup"><span data-stu-id="485b2-128">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="485b2-129">各メソッドは独自の修飾子を持つことができるため、 [IWbemQualifierSet ポインター](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)によって呼び出し元はこれらの修飾子を追加、編集、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="485b2-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="485b2-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="485b2-130">Requirements</span></span>

<span data-ttu-id="485b2-131">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="485b2-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="485b2-132">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="485b2-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="485b2-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="485b2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="485b2-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="485b2-134">See also</span></span>

- [<span data-ttu-id="485b2-135">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="485b2-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

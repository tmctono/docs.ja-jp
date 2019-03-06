---
title: Delete 関数 (アンマネージ API リファレンス)
description: 機能の削除は、CIM クラスの定義から、指定したプロパティとその修飾子のすべてを削除します。
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1a26db7785a8a378fa541308ecc6aee30fa87ec
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367127"
---
# <a name="delete-function"></a><span data-ttu-id="07bf1-103">関数を削除します。</span><span class="sxs-lookup"><span data-stu-id="07bf1-103">Delete function</span></span>

<span data-ttu-id="07bf1-104">CIM クラスの定義から、指定したプロパティとその修飾子のすべてを削除します。</span><span class="sxs-lookup"><span data-stu-id="07bf1-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="07bf1-105">構文</span><span class="sxs-lookup"><span data-stu-id="07bf1-105">Syntax</span></span>

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a><span data-ttu-id="07bf1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="07bf1-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="07bf1-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="07bf1-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="07bf1-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="07bf1-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="07bf1-109">[in]削除するプロパティの名前。</span><span class="sxs-lookup"><span data-stu-id="07bf1-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="07bf1-110">`wszName` 有効なポインターである必要があります`LPCWSTR`します。</span><span class="sxs-lookup"><span data-stu-id="07bf1-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="07bf1-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="07bf1-111">Return value</span></span>

<span data-ttu-id="07bf1-112">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="07bf1-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="07bf1-113">定数</span><span class="sxs-lookup"><span data-stu-id="07bf1-113">Constant</span></span>  |<span data-ttu-id="07bf1-114">値</span><span class="sxs-lookup"><span data-stu-id="07bf1-114">Value</span></span>  |<span data-ttu-id="07bf1-115">説明</span><span class="sxs-lookup"><span data-stu-id="07bf1-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="07bf1-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="07bf1-116">0x80041001</span></span> | <span data-ttu-id="07bf1-117">不明なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="07bf1-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="07bf1-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="07bf1-118">0x80041016</span></span> | <span data-ttu-id="07bf1-119">プロパティを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="07bf1-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="07bf1-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="07bf1-120">0x80041008</span></span> | <span data-ttu-id="07bf1-121">`wszName` が無効です。</span><span class="sxs-lookup"><span data-stu-id="07bf1-121">`wszName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="07bf1-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="07bf1-122">0x80041002</span></span> | <span data-ttu-id="07bf1-123">指定したプロパティが存在しません。</span><span class="sxs-lookup"><span data-stu-id="07bf1-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="07bf1-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="07bf1-124">0x80041006</span></span> | <span data-ttu-id="07bf1-125">操作を完了するのに十分なメモリがありません。</span><span class="sxs-lookup"><span data-stu-id="07bf1-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="07bf1-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="07bf1-126">0x8004101c</span></span> | <span data-ttu-id="07bf1-127">プロパティは、基本クラスから継承されます。</span><span class="sxs-lookup"><span data-stu-id="07bf1-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="07bf1-128">プロパティは、システム プロパティです。</span><span class="sxs-lookup"><span data-stu-id="07bf1-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="07bf1-129">0</span><span class="sxs-lookup"><span data-stu-id="07bf1-129">0</span></span> | <span data-ttu-id="07bf1-130">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="07bf1-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="07bf1-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="07bf1-131">0x80041030</span></span> | <span data-ttu-id="07bf1-132">関数は、現在のクラスを上書きする既定値を削除します。</span><span class="sxs-lookup"><span data-stu-id="07bf1-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="07bf1-133">親クラスでは、このプロパティの既定値が再アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="07bf1-133">The default value for this property in the parent class has been reactivated.</span></span> |

## <a name="remarks"></a><span data-ttu-id="07bf1-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="07bf1-134">Remarks</span></span>

<span data-ttu-id="07bf1-135">この関数の呼び出しをラップする、 [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete)メソッド。</span><span class="sxs-lookup"><span data-stu-id="07bf1-135">This function wraps a call to the [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="07bf1-136">必要条件</span><span class="sxs-lookup"><span data-stu-id="07bf1-136">Requirements</span></span>

<span data-ttu-id="07bf1-137">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07bf1-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="07bf1-138">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="07bf1-138">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="07bf1-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="07bf1-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="07bf1-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="07bf1-140">See also</span></span>

- [<span data-ttu-id="07bf1-141">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="07bf1-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
---
title: Delete 関数 (アンマネージ API リファレンス)
description: Delete 関数は、指定されたプロパティとそのすべての修飾子を CIM クラス定義から削除します。
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
ms.openlocfilehash: 6b8f287be831702dd31a8335f9b2f6447bcee540
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127664"
---
# <a name="delete-function"></a><span data-ttu-id="d3fc9-103">Delete 関数</span><span class="sxs-lookup"><span data-stu-id="d3fc9-103">Delete function</span></span>

<span data-ttu-id="d3fc9-104">指定したプロパティとそのすべての修飾子を CIM クラス定義から削除します。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d3fc9-105">構文</span><span class="sxs-lookup"><span data-stu-id="d3fc9-105">Syntax</span></span>

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a><span data-ttu-id="d3fc9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d3fc9-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="d3fc9-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="d3fc9-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="d3fc9-109">から削除するプロパティの名前。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="d3fc9-110">`wszName` は、有効な `LPCWSTR`へのポインターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="d3fc9-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="d3fc9-111">Return value</span></span>

<span data-ttu-id="d3fc9-112">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d3fc9-113">定数</span><span class="sxs-lookup"><span data-stu-id="d3fc9-113">Constant</span></span>  |<span data-ttu-id="d3fc9-114">[値]</span><span class="sxs-lookup"><span data-stu-id="d3fc9-114">Value</span></span>  |<span data-ttu-id="d3fc9-115">説明</span><span class="sxs-lookup"><span data-stu-id="d3fc9-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="d3fc9-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="d3fc9-116">0x80041001</span></span> | <span data-ttu-id="d3fc9-117">特定できないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="d3fc9-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="d3fc9-118">0x80041016</span></span> | <span data-ttu-id="d3fc9-119">プロパティを削除できません。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d3fc9-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d3fc9-120">0x80041008</span></span> | <span data-ttu-id="d3fc9-121">`wszName` が無効です。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-121">`wszName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="d3fc9-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="d3fc9-122">0x80041002</span></span> | <span data-ttu-id="d3fc9-123">指定されたプロパティが存在しません。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d3fc9-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d3fc9-124">0x80041006</span></span> | <span data-ttu-id="d3fc9-125">操作を完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="d3fc9-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="d3fc9-126">0x8004101c</span></span> | <span data-ttu-id="d3fc9-127">プロパティは、基本クラスから継承されます。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="d3fc9-128">プロパティはシステムプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d3fc9-129">0</span><span class="sxs-lookup"><span data-stu-id="d3fc9-129">0</span></span> | <span data-ttu-id="d3fc9-130">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="d3fc9-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="d3fc9-131">0x80041030</span></span> | <span data-ttu-id="d3fc9-132">関数は、現在のクラスのオーバーライドの既定値を削除しました。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="d3fc9-133">親クラスのこのプロパティの既定値は再アクティブ化されています。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-133">The default value for this property in the parent class has been reactivated.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d3fc9-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="d3fc9-134">Remarks</span></span>

<span data-ttu-id="d3fc9-135">この関数は、 [IWbemClassObject::D e)](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-135">This function wraps a call to the [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d3fc9-136">［要件］</span><span class="sxs-lookup"><span data-stu-id="d3fc9-136">Requirements</span></span>

<span data-ttu-id="d3fc9-137">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3fc9-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d3fc9-138">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="d3fc9-138">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="d3fc9-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d3fc9-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d3fc9-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3fc9-140">See also</span></span>

- [<span data-ttu-id="d3fc9-141">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d3fc9-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

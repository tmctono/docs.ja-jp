---
title: QualifierSet_Put 関数 (アンマネージ API リファレンス)
description: QualifierSet_Put 関数は、名前付きの修飾子とその値を書き込みます。
ms.date: 11/06/2017
api_name:
- QualifierSet_Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Put
helpviewer_keywords:
- QualifierSet_Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e42cf3440bef030f5c7bec71ed1b4b875b79a61
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378835"
---
# <a name="qualifiersetput-function"></a><span data-ttu-id="4349e-103">QualifierSet_Put 関数</span><span class="sxs-lookup"><span data-stu-id="4349e-103">QualifierSet_Put function</span></span>

<span data-ttu-id="4349e-104">名前付き修飾子と値が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="4349e-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="4349e-105">新しい修飾子は、同じ名前の前の値を上書きします。</span><span class="sxs-lookup"><span data-stu-id="4349e-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="4349e-106">修飾子が存在しない場合は作成されます。</span><span class="sxs-lookup"><span data-stu-id="4349e-106">If the qualifier does not exist, it is created.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="4349e-107">構文</span><span class="sxs-lookup"><span data-stu-id="4349e-107">Syntax</span></span>

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="4349e-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4349e-108">Parameters</span></span>

`vFunc`\
<span data-ttu-id="4349e-109">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="4349e-109">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="4349e-110">[in]ポインター、 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="4349e-110">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`\
<span data-ttu-id="4349e-111">[in]書き込む修飾子の名前。</span><span class="sxs-lookup"><span data-stu-id="4349e-111">[in] The name of the qualifier to write.</span></span>

`pVal`\
<span data-ttu-id="4349e-112">[in]有効なへのポインター`VARIANT`書き込む修飾子を格納しています。</span><span class="sxs-lookup"><span data-stu-id="4349e-112">[in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="4349e-113">このパラメーターを `null` とすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4349e-113">This parameter cannot be `null`.</span></span>

`lFlavor`\
<span data-ttu-id="4349e-114">[in]この修飾子の必要な修飾子のフレーバーを定義する次の定数の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="4349e-114">[in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="4349e-115">既定値は`WBEM_FLAVOR_OVERRIDABLE`(0)。</span><span class="sxs-lookup"><span data-stu-id="4349e-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="4349e-116">定数</span><span class="sxs-lookup"><span data-stu-id="4349e-116">Constant</span></span>  |<span data-ttu-id="4349e-117">値</span><span class="sxs-lookup"><span data-stu-id="4349e-117">Value</span></span>  |<span data-ttu-id="4349e-118">説明</span><span class="sxs-lookup"><span data-stu-id="4349e-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="4349e-119">0</span><span class="sxs-lookup"><span data-stu-id="4349e-119">0</span></span> | <span data-ttu-id="4349e-120">修飾子は、派生クラスまたはインスタンスでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="4349e-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="4349e-121">**これは、既定値です。**</span><span class="sxs-lookup"><span data-stu-id="4349e-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="4349e-122">1</span><span class="sxs-lookup"><span data-stu-id="4349e-122">1</span></span> | <span data-ttu-id="4349e-123">この修飾子は、インスタンスに反映されます。</span><span class="sxs-lookup"><span data-stu-id="4349e-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="4349e-124">2</span><span class="sxs-lookup"><span data-stu-id="4349e-124">2</span></span> | <span data-ttu-id="4349e-125">修飾子は、派生クラスに反映します。</span><span class="sxs-lookup"><span data-stu-id="4349e-125">The qualifier is propagated to derived classes.</span></span> |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | <span data-ttu-id="4349e-126">0x10</span><span class="sxs-lookup"><span data-stu-id="4349e-126">0x10</span></span> | <span data-ttu-id="4349e-127">この修飾子は、派生クラスまたはインスタンスではオーバーライドできません。</span><span class="sxs-lookup"><span data-stu-id="4349e-127">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| `WBEM_FLAVOR_AMENDED` | <span data-ttu-id="4349e-128">0x80</span><span class="sxs-lookup"><span data-stu-id="4349e-128">0x80</span></span> | <span data-ttu-id="4349e-129">修飾子がローカライズされます。</span><span class="sxs-lookup"><span data-stu-id="4349e-129">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="4349e-130">戻り値</span><span class="sxs-lookup"><span data-stu-id="4349e-130">Return value</span></span>

<span data-ttu-id="4349e-131">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="4349e-131">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4349e-132">定数</span><span class="sxs-lookup"><span data-stu-id="4349e-132">Constant</span></span>  |<span data-ttu-id="4349e-133">値</span><span class="sxs-lookup"><span data-stu-id="4349e-133">Value</span></span>  |<span data-ttu-id="4349e-134">説明</span><span class="sxs-lookup"><span data-stu-id="4349e-134">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="4349e-135">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="4349e-135">0x8004101f</span></span> | <span data-ttu-id="4349e-136">指定する無効なが試行されました、**キー**修飾子プロパティのキーにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4349e-136">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="4349e-137">キーが指定された om c; オブジェクトのクラス定義し、インスタンスごとに変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="4349e-137">The keys are specified om tje c;ass definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4349e-138">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4349e-138">0x80041008</span></span> | <span data-ttu-id="4349e-139">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="4349e-139">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="4349e-140">0x80041029</span><span class="sxs-lookup"><span data-stu-id="4349e-140">0x80041029</span></span> | <span data-ttu-id="4349e-141">`pVal`パラメーターが有効な修飾子型ではありません。</span><span class="sxs-lookup"><span data-stu-id="4349e-141">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="4349e-142">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="4349e-142">0x8004101a</span></span> | <span data-ttu-id="4349e-143">呼び出すことはできません、`QualifierSet_Put`メソッド修飾子を所有するオブジェクトが許可されていないためにオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="4349e-143">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="4349e-144">0</span><span class="sxs-lookup"><span data-stu-id="4349e-144">0</span></span> | <span data-ttu-id="4349e-145">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="4349e-145">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="4349e-146">Remarks</span><span class="sxs-lookup"><span data-stu-id="4349e-146">Remarks</span></span>

<span data-ttu-id="4349e-147">この関数の呼び出しをラップする、 [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put)メソッド。</span><span class="sxs-lookup"><span data-stu-id="4349e-147">This function wraps a call to the [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="4349e-148">必要条件</span><span class="sxs-lookup"><span data-stu-id="4349e-148">Requirements</span></span>

<span data-ttu-id="4349e-149">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4349e-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="4349e-150">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4349e-150">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="4349e-151">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4349e-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4349e-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="4349e-152">See also</span></span>

- [<span data-ttu-id="4349e-153">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="4349e-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
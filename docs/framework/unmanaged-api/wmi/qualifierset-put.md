---
title: QualifierSet_Put 関数 (アンマネージ API リファレンス)
description: QualifierSet_Put 関数は、名前付き修飾子とその値を書き込みます。
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
ms.openlocfilehash: a35025c6d16455a51b7b22d822ba77337ddd894a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120235"
---
# <a name="qualifierset_put-function"></a><span data-ttu-id="3a63b-103">QualifierSet_Put 関数</span><span class="sxs-lookup"><span data-stu-id="3a63b-103">QualifierSet_Put function</span></span>

<span data-ttu-id="3a63b-104">名前付き修飾子と値が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="3a63b-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="3a63b-105">新しい修飾子は、同じ名前の前の値を上書きします。</span><span class="sxs-lookup"><span data-stu-id="3a63b-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="3a63b-106">修飾子が存在しない場合は、作成されます。</span><span class="sxs-lookup"><span data-stu-id="3a63b-106">If the qualifier does not exist, it is created.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="3a63b-107">構文</span><span class="sxs-lookup"><span data-stu-id="3a63b-107">Syntax</span></span>

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="3a63b-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a63b-108">Parameters</span></span>

`vFunc`\
<span data-ttu-id="3a63b-109">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="3a63b-109">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="3a63b-110">から[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3a63b-110">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`\
<span data-ttu-id="3a63b-111">から書き込む修飾子の名前。</span><span class="sxs-lookup"><span data-stu-id="3a63b-111">[in] The name of the qualifier to write.</span></span>

`pVal`\
<span data-ttu-id="3a63b-112">から書き込む修飾子を含む有効な `VARIANT` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3a63b-112">[in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="3a63b-113">このパラメーターを `null` とすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3a63b-113">This parameter cannot be `null`.</span></span>

`lFlavor`\
<span data-ttu-id="3a63b-114">からこの修飾子に必要な修飾子の種類を定義する、次のいずれかの定数。</span><span class="sxs-lookup"><span data-stu-id="3a63b-114">[in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="3a63b-115">既定値は `WBEM_FLAVOR_OVERRIDABLE` (0) です。</span><span class="sxs-lookup"><span data-stu-id="3a63b-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="3a63b-116">定数</span><span class="sxs-lookup"><span data-stu-id="3a63b-116">Constant</span></span>  |<span data-ttu-id="3a63b-117">[値]</span><span class="sxs-lookup"><span data-stu-id="3a63b-117">Value</span></span>  |<span data-ttu-id="3a63b-118">説明</span><span class="sxs-lookup"><span data-stu-id="3a63b-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="3a63b-119">0</span><span class="sxs-lookup"><span data-stu-id="3a63b-119">0</span></span> | <span data-ttu-id="3a63b-120">修飾子は、派生クラスまたは派生インスタンスでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="3a63b-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="3a63b-121">**これが既定値です。**</span><span class="sxs-lookup"><span data-stu-id="3a63b-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="3a63b-122">1</span><span class="sxs-lookup"><span data-stu-id="3a63b-122">1</span></span> | <span data-ttu-id="3a63b-123">この修飾子は、インスタンスに反映されます。</span><span class="sxs-lookup"><span data-stu-id="3a63b-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="3a63b-124">2</span><span class="sxs-lookup"><span data-stu-id="3a63b-124">2</span></span> | <span data-ttu-id="3a63b-125">修飾子は、派生クラスに反映されます。</span><span class="sxs-lookup"><span data-stu-id="3a63b-125">The qualifier is propagated to derived classes.</span></span> |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | <span data-ttu-id="3a63b-126">0x10</span><span class="sxs-lookup"><span data-stu-id="3a63b-126">0x10</span></span> | <span data-ttu-id="3a63b-127">この修飾子は、派生クラスまたはインスタンスではオーバーライドできません。</span><span class="sxs-lookup"><span data-stu-id="3a63b-127">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| `WBEM_FLAVOR_AMENDED` | <span data-ttu-id="3a63b-128">0x80</span><span class="sxs-lookup"><span data-stu-id="3a63b-128">0x80</span></span> | <span data-ttu-id="3a63b-129">修飾子はローカライズされています。</span><span class="sxs-lookup"><span data-stu-id="3a63b-129">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="3a63b-130">戻り値</span><span class="sxs-lookup"><span data-stu-id="3a63b-130">Return value</span></span>

<span data-ttu-id="3a63b-131">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="3a63b-131">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3a63b-132">定数</span><span class="sxs-lookup"><span data-stu-id="3a63b-132">Constant</span></span>  |<span data-ttu-id="3a63b-133">[値]</span><span class="sxs-lookup"><span data-stu-id="3a63b-133">Value</span></span>  |<span data-ttu-id="3a63b-134">説明</span><span class="sxs-lookup"><span data-stu-id="3a63b-134">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="3a63b-135">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="3a63b-135">0x8004101f</span></span> | <span data-ttu-id="3a63b-136">キーにすることができないプロパティで**キー**修飾子を指定しようとしましたが、無効です。</span><span class="sxs-lookup"><span data-stu-id="3a63b-136">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="3a63b-137">キーは、オブジェクトのクラス定義で指定され、インスタンスごとに変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a63b-137">The keys are specified in the class definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3a63b-138">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3a63b-138">0x80041008</span></span> | <span data-ttu-id="3a63b-139">パラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="3a63b-139">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="3a63b-140">0x8004-9</span><span class="sxs-lookup"><span data-stu-id="3a63b-140">0x80041029</span></span> | <span data-ttu-id="3a63b-141">`pVal` パラメーターが有効な修飾子の型ではありません。</span><span class="sxs-lookup"><span data-stu-id="3a63b-141">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="3a63b-142">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="3a63b-142">0x8004101a</span></span> | <span data-ttu-id="3a63b-143">所有オブジェクトではオーバーライドが許可されていないため、修飾子で `QualifierSet_Put` メソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="3a63b-143">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="3a63b-144">0</span><span class="sxs-lookup"><span data-stu-id="3a63b-144">0</span></span> | <span data-ttu-id="3a63b-145">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="3a63b-145">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="3a63b-146">Remarks</span><span class="sxs-lookup"><span data-stu-id="3a63b-146">Remarks</span></span>

<span data-ttu-id="3a63b-147">この関数は、 [IWbemQualifierSet::P ut](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="3a63b-147">This function wraps a call to the [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3a63b-148">［要件］</span><span class="sxs-lookup"><span data-stu-id="3a63b-148">Requirements</span></span>

<span data-ttu-id="3a63b-149">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a63b-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="3a63b-150">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="3a63b-150">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="3a63b-151">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3a63b-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3a63b-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a63b-152">See also</span></span>

- [<span data-ttu-id="3a63b-153">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3a63b-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

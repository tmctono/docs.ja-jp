---
title: CompareTo 関数 (アンマネージ API リファレンス)
description: CompareTo 関数は、オブジェクトを別の WMI オブジェクトと比較します。
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0d210795016cd2e0179b902a224ca0c62f4ac01f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128705"
---
# <a name="compareto-function"></a><span data-ttu-id="22e6d-103">CompareTo 関数</span><span class="sxs-lookup"><span data-stu-id="22e6d-103">CompareTo function</span></span>

<span data-ttu-id="22e6d-104">オブジェクトが、別の Windows 管理オブジェクトと比較されます。</span><span class="sxs-lookup"><span data-stu-id="22e6d-104">Compares an object to another Windows management object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="22e6d-105">構文</span><span class="sxs-lookup"><span data-stu-id="22e6d-105">Syntax</span></span>

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a><span data-ttu-id="22e6d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="22e6d-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="22e6d-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="22e6d-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="22e6d-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="22e6d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`flags`\
<span data-ttu-id="22e6d-109">から比較のために考慮するオブジェクト特性を指定するフラグのビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="22e6d-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="22e6d-110">詳細については、「[解説](#remarks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22e6d-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`\
<span data-ttu-id="22e6d-111">から比較対象のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="22e6d-111">[in] The object for comparison.</span></span> <span data-ttu-id="22e6d-112">`pCompareTo` 有効な[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスである必要があります。`null`することはできません。</span><span class="sxs-lookup"><span data-stu-id="22e6d-112">`pCompareTo` must be a valid [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="22e6d-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="22e6d-113">Return value</span></span>

<span data-ttu-id="22e6d-114">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="22e6d-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="22e6d-115">定数</span><span class="sxs-lookup"><span data-stu-id="22e6d-115">Constant</span></span>  |<span data-ttu-id="22e6d-116">[値]</span><span class="sxs-lookup"><span data-stu-id="22e6d-116">Value</span></span>  |<span data-ttu-id="22e6d-117">説明</span><span class="sxs-lookup"><span data-stu-id="22e6d-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="22e6d-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="22e6d-118">0x80041001</span></span> | <span data-ttu-id="22e6d-119">特定できないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="22e6d-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="22e6d-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="22e6d-120">0x80041008</span></span> | <span data-ttu-id="22e6d-121">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="22e6d-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="22e6d-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="22e6d-122">0x8004101d</span></span> | <span data-ttu-id="22e6d-123">`BeginEnumeration` の2回目の呼び出しが、 [`EndEnumeration`](endenumeration.md)の介在する呼び出しなしで行われました。</span><span class="sxs-lookup"><span data-stu-id="22e6d-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="22e6d-124">0</span><span class="sxs-lookup"><span data-stu-id="22e6d-124">0</span></span> | <span data-ttu-id="22e6d-125">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="22e6d-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="22e6d-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="22e6d-126">0x40003</span></span> | <span data-ttu-id="22e6d-127">オブジェクトが異なります。</span><span class="sxs-lookup"><span data-stu-id="22e6d-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="22e6d-128">0</span><span class="sxs-lookup"><span data-stu-id="22e6d-128">0</span></span> | <span data-ttu-id="22e6d-129">これらのオブジェクトは、比較フラグに基づいています。</span><span class="sxs-lookup"><span data-stu-id="22e6d-129">The objects are the same based on the comparison flags.</span></span> |

## <a name="remarks"></a><span data-ttu-id="22e6d-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="22e6d-130">Remarks</span></span>

<span data-ttu-id="22e6d-131">この関数は、 [IWbemClassObject:: CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="22e6d-131">This function wraps a call to the [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) method.</span></span>

<span data-ttu-id="22e6d-132">`lEnumFlags` 引数として渡すことができるフラグは、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="22e6d-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="22e6d-133">次のフラグのビットごとの組み合わせを指定することで、比較に含まれる個々の特性を指定できます。</span><span class="sxs-lookup"><span data-stu-id="22e6d-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="22e6d-134">定数</span><span class="sxs-lookup"><span data-stu-id="22e6d-134">Constant</span></span>  |<span data-ttu-id="22e6d-135">[値]</span><span class="sxs-lookup"><span data-stu-id="22e6d-135">Value</span></span>  |<span data-ttu-id="22e6d-136">説明</span><span class="sxs-lookup"><span data-stu-id="22e6d-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="22e6d-137">2</span><span class="sxs-lookup"><span data-stu-id="22e6d-137">2</span></span> | <span data-ttu-id="22e6d-138">ソース (サーバーとその元の名前空間) を無視します。</span><span class="sxs-lookup"><span data-stu-id="22e6d-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="22e6d-139">1</span><span class="sxs-lookup"><span data-stu-id="22e6d-139">1</span></span> | <span data-ttu-id="22e6d-140">すべての修飾子を無視する (**キー**と**動的**を含む)</span><span class="sxs-lookup"><span data-stu-id="22e6d-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="22e6d-141">4</span><span class="sxs-lookup"><span data-stu-id="22e6d-141">4</span></span> | <span data-ttu-id="22e6d-142">プロパティの既定値を無視します。</span><span class="sxs-lookup"><span data-stu-id="22e6d-142">Ignore default values of properties.</span></span> <span data-ttu-id="22e6d-143">このフラグは、クラスの比較にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="22e6d-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="22e6d-144">0x20</span><span class="sxs-lookup"><span data-stu-id="22e6d-144">0x20</span></span> | <span data-ttu-id="22e6d-145">修飾子の種類を無視します。</span><span class="sxs-lookup"><span data-stu-id="22e6d-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="22e6d-146">このフラグは引き続き修飾子を考慮しますが、伝達規則やオーバーライドの制限などのフレーバーの違いは無視します。</span><span class="sxs-lookup"><span data-stu-id="22e6d-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="22e6d-147">0x10</span><span class="sxs-lookup"><span data-stu-id="22e6d-147">0x10</span></span> | <span data-ttu-id="22e6d-148">文字列値の比較で大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="22e6d-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="22e6d-149">これは、文字列と修飾子の値の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="22e6d-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="22e6d-150">プロパティと修飾子の名前の比較では、このフラグが設定されているかどうかに関係なく、常に大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="22e6d-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="22e6d-151">0x8</span><span class="sxs-lookup"><span data-stu-id="22e6d-151">0x8</span></span> | <span data-ttu-id="22e6d-152">比較対象のオブジェクトが同じクラスのインスタンスであると仮定します。</span><span class="sxs-lookup"><span data-stu-id="22e6d-152">Assume that the objects being compared are instances of the same class.</span></span> <span data-ttu-id="22e6d-153">その結果、このフラグは、インスタンス関連の情報のみを比較します。</span><span class="sxs-lookup"><span data-stu-id="22e6d-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="22e6d-154">パフォーマンスを最適化するには、このフラグを使用します。</span><span class="sxs-lookup"><span data-stu-id="22e6d-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="22e6d-155">オブジェクトが同じクラスではない場合、結果は未定義になります。</span><span class="sxs-lookup"><span data-stu-id="22e6d-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="22e6d-156">または、次のように1つの複合フラグを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="22e6d-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="22e6d-157">定数</span><span class="sxs-lookup"><span data-stu-id="22e6d-157">Constant</span></span>  |<span data-ttu-id="22e6d-158">[値]</span><span class="sxs-lookup"><span data-stu-id="22e6d-158">Value</span></span>  |<span data-ttu-id="22e6d-159">説明</span><span class="sxs-lookup"><span data-stu-id="22e6d-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="22e6d-160">0</span><span class="sxs-lookup"><span data-stu-id="22e6d-160">0</span></span> | <span data-ttu-id="22e6d-161">比較のすべての機能を検討します。</span><span class="sxs-lookup"><span data-stu-id="22e6d-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="22e6d-162">［要件］</span><span class="sxs-lookup"><span data-stu-id="22e6d-162">Requirements</span></span>

<span data-ttu-id="22e6d-163">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22e6d-163">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="22e6d-164">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="22e6d-164">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="22e6d-165">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="22e6d-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="22e6d-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="22e6d-166">See also</span></span>

- [<span data-ttu-id="22e6d-167">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="22e6d-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

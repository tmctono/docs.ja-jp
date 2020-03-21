---
title: 列挙関数 (アンマネージ API リファレンス)
description: 列挙子を列挙の先頭にリセットします。
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: eac23916bd78ec3970a87566e2d2f4d79b379824
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176878"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="62f0d-103">BeginEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="62f0d-103">BeginEnumeration function</span></span>
<span data-ttu-id="62f0d-104">列挙子を列挙の先頭にリセットします。</span><span class="sxs-lookup"><span data-stu-id="62f0d-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="62f0d-105">構文</span><span class="sxs-lookup"><span data-stu-id="62f0d-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a><span data-ttu-id="62f0d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="62f0d-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="62f0d-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="62f0d-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="62f0d-108">[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="62f0d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="62f0d-109">[in]列挙体に含まれるプロパティを制御する[「解説」](#remarks)セクションで説明されているフラグまたは値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="62f0d-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="62f0d-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="62f0d-110">Return value</span></span>

<span data-ttu-id="62f0d-111">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="62f0d-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="62f0d-112">常時</span><span class="sxs-lookup"><span data-stu-id="62f0d-112">Constant</span></span>  |<span data-ttu-id="62f0d-113">Value</span><span class="sxs-lookup"><span data-stu-id="62f0d-113">Value</span></span>  |<span data-ttu-id="62f0d-114">説明</span><span class="sxs-lookup"><span data-stu-id="62f0d-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="62f0d-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="62f0d-115">0x80041008</span></span> | <span data-ttu-id="62f0d-116">フラグの組み合`lEnumFlags`わせが無効か、無効な引数が指定されました。</span><span class="sxs-lookup"><span data-stu-id="62f0d-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="62f0d-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="62f0d-117">0x8004101d</span></span> | <span data-ttu-id="62f0d-118">への 2`BeginEnumeration`回目の呼び出しは、間[`EndEnumeration`](endenumeration.md)に呼び出されることなく行われました。</span><span class="sxs-lookup"><span data-stu-id="62f0d-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="62f0d-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="62f0d-119">0x80041006</span></span> | <span data-ttu-id="62f0d-120">メモリ不足で新しい列挙を開始できません。</span><span class="sxs-lookup"><span data-stu-id="62f0d-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="62f0d-121">0</span><span class="sxs-lookup"><span data-stu-id="62f0d-121">0</span></span> | <span data-ttu-id="62f0d-122">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="62f0d-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="62f0d-123">解説</span><span class="sxs-lookup"><span data-stu-id="62f0d-123">Remarks</span></span>

<span data-ttu-id="62f0d-124">この関数は、[メソッド](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)の呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="62f0d-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="62f0d-125">`lEnumFlags`引数として渡すことができるフラグは *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="62f0d-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="62f0d-126">各グループの 1 つのフラグを、他のグループの任意のフラグと組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="62f0d-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="62f0d-127">ただし、同じグループのフラグは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="62f0d-127">However, flags from the same group are mutually exclusive.</span></span>

<span data-ttu-id="62f0d-128">**グループ 1**</span><span class="sxs-lookup"><span data-stu-id="62f0d-128">**Group 1**</span></span>

|<span data-ttu-id="62f0d-129">常時</span><span class="sxs-lookup"><span data-stu-id="62f0d-129">Constant</span></span>  |<span data-ttu-id="62f0d-130">Value</span><span class="sxs-lookup"><span data-stu-id="62f0d-130">Value</span></span>  |<span data-ttu-id="62f0d-131">説明</span><span class="sxs-lookup"><span data-stu-id="62f0d-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="62f0d-132">0x4</span><span class="sxs-lookup"><span data-stu-id="62f0d-132">0x4</span></span> | <span data-ttu-id="62f0d-133">キーのみを構成するプロパティを含めます。</span><span class="sxs-lookup"><span data-stu-id="62f0d-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="62f0d-134">0x8</span><span class="sxs-lookup"><span data-stu-id="62f0d-134">0x8</span></span> | <span data-ttu-id="62f0d-135">オブジェクト参照だけのプロパティを含めます。</span><span class="sxs-lookup"><span data-stu-id="62f0d-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="62f0d-136">**グループ 2**</span><span class="sxs-lookup"><span data-stu-id="62f0d-136">**Group 2**</span></span>

<span data-ttu-id="62f0d-137">常時</span><span class="sxs-lookup"><span data-stu-id="62f0d-137">Constant</span></span>  |<span data-ttu-id="62f0d-138">Value</span><span class="sxs-lookup"><span data-stu-id="62f0d-138">Value</span></span>  |<span data-ttu-id="62f0d-139">説明</span><span class="sxs-lookup"><span data-stu-id="62f0d-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="62f0d-140">0x30</span><span class="sxs-lookup"><span data-stu-id="62f0d-140">0x30</span></span> | <span data-ttu-id="62f0d-141">列挙をシステム プロパティのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="62f0d-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="62f0d-142">0x40</span><span class="sxs-lookup"><span data-stu-id="62f0d-142">0x40</span></span> | <span data-ttu-id="62f0d-143">ローカル プロパティと反映プロパティを含めますが、列挙体からシステム プロパティを除外します。</span><span class="sxs-lookup"><span data-stu-id="62f0d-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="62f0d-144">クラスの場合:</span><span class="sxs-lookup"><span data-stu-id="62f0d-144">For classes:</span></span>

<span data-ttu-id="62f0d-145">常時</span><span class="sxs-lookup"><span data-stu-id="62f0d-145">Constant</span></span>  |<span data-ttu-id="62f0d-146">Value</span><span class="sxs-lookup"><span data-stu-id="62f0d-146">Value</span></span>  |<span data-ttu-id="62f0d-147">説明</span><span class="sxs-lookup"><span data-stu-id="62f0d-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="62f0d-148">0x100</span><span class="sxs-lookup"><span data-stu-id="62f0d-148">0x100</span></span> | <span data-ttu-id="62f0d-149">列挙型をクラス定義でオーバーライドされたプロパティに制限します。</span><span class="sxs-lookup"><span data-stu-id="62f0d-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="62f0d-150">0x100</span><span class="sxs-lookup"><span data-stu-id="62f0d-150">0x100</span></span> | <span data-ttu-id="62f0d-151">列挙型を、現在のクラス定義でオーバーライドされたプロパティと、クラスで定義された新しいプロパティに制限します。</span><span class="sxs-lookup"><span data-stu-id="62f0d-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="62f0d-152">0x300</span><span class="sxs-lookup"><span data-stu-id="62f0d-152">0x300</span></span> | <span data-ttu-id="62f0d-153">いずれかの`WBEM_FLAG_CLASS_OVERRIDES_ONLY`値が設定されているか、または`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES`設定されているかを確認する`lEnumFlags`値に適用するマスク (フラグではなく) です。</span><span class="sxs-lookup"><span data-stu-id="62f0d-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="62f0d-154">0x10</span><span class="sxs-lookup"><span data-stu-id="62f0d-154">0x10</span></span> | <span data-ttu-id="62f0d-155">列挙型を、クラス自体で定義または変更されたプロパティに制限します。</span><span class="sxs-lookup"><span data-stu-id="62f0d-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="62f0d-156">0x20</span><span class="sxs-lookup"><span data-stu-id="62f0d-156">0x20</span></span> | <span data-ttu-id="62f0d-157">列挙型を、基本クラスから継承されるプロパティに制限します。</span><span class="sxs-lookup"><span data-stu-id="62f0d-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="62f0d-158">インスタンスの場合:</span><span class="sxs-lookup"><span data-stu-id="62f0d-158">For instances:</span></span>

<span data-ttu-id="62f0d-159">常時</span><span class="sxs-lookup"><span data-stu-id="62f0d-159">Constant</span></span>  |<span data-ttu-id="62f0d-160">Value</span><span class="sxs-lookup"><span data-stu-id="62f0d-160">Value</span></span>  |<span data-ttu-id="62f0d-161">説明</span><span class="sxs-lookup"><span data-stu-id="62f0d-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="62f0d-162">0x10</span><span class="sxs-lookup"><span data-stu-id="62f0d-162">0x10</span></span> | <span data-ttu-id="62f0d-163">列挙型を、クラス自体で定義または変更されたプロパティに制限します。</span><span class="sxs-lookup"><span data-stu-id="62f0d-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="62f0d-164">0x20</span><span class="sxs-lookup"><span data-stu-id="62f0d-164">0x20</span></span> | <span data-ttu-id="62f0d-165">列挙型を、基本クラスから継承されるプロパティに制限します。</span><span class="sxs-lookup"><span data-stu-id="62f0d-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="62f0d-166">必要条件</span><span class="sxs-lookup"><span data-stu-id="62f0d-166">Requirements</span></span>  
 <span data-ttu-id="62f0d-167">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62f0d-167">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62f0d-168">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="62f0d-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="62f0d-169">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="62f0d-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62f0d-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="62f0d-170">See also</span></span>

- [<span data-ttu-id="62f0d-171">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="62f0d-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

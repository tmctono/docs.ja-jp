---
title: BeginEnumeration 関数 (アンマネージ API リファレンス)
description: BeginEnumeration 関数は、列挙子を列挙体の先頭にリセットします。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de36650aa2b206b5e9734b38c6067a3a79de610c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798784"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="78c5f-103">BeginEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="78c5f-103">BeginEnumeration function</span></span>
<span data-ttu-id="78c5f-104">列挙子を列挙体の先頭にリセットします。</span><span class="sxs-lookup"><span data-stu-id="78c5f-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="78c5f-105">構文</span><span class="sxs-lookup"><span data-stu-id="78c5f-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="78c5f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="78c5f-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="78c5f-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="78c5f-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="78c5f-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="78c5f-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="78c5f-109">から列挙に含まれるプロパティを制御する、「[解説](#remarks)」で説明されているフラグまたは値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="78c5f-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="78c5f-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="78c5f-110">Return value</span></span>

<span data-ttu-id="78c5f-111">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="78c5f-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="78c5f-112">定数</span><span class="sxs-lookup"><span data-stu-id="78c5f-112">Constant</span></span>  |<span data-ttu-id="78c5f-113">Value</span><span class="sxs-lookup"><span data-stu-id="78c5f-113">Value</span></span>  |<span data-ttu-id="78c5f-114">説明</span><span class="sxs-lookup"><span data-stu-id="78c5f-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="78c5f-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="78c5f-115">0x80041008</span></span> | <span data-ttu-id="78c5f-116">の`lEnumFlags`フラグの組み合わせが無効であるか、無効な引数が指定されました。</span><span class="sxs-lookup"><span data-stu-id="78c5f-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="78c5f-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="78c5f-117">0x8004101d</span></span> | <span data-ttu-id="78c5f-118">への2回`BeginEnumeration`目の呼び出しは、の間[`EndEnumeration`](endenumeration.md)の呼び出しなしで行われました。</span><span class="sxs-lookup"><span data-stu-id="78c5f-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="78c5f-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="78c5f-119">0x80041006</span></span> | <span data-ttu-id="78c5f-120">新しい列挙を開始するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="78c5f-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="78c5f-121">0</span><span class="sxs-lookup"><span data-stu-id="78c5f-121">0</span></span> | <span data-ttu-id="78c5f-122">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="78c5f-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="78c5f-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="78c5f-123">Remarks</span></span>

<span data-ttu-id="78c5f-124">この関数は、 [IWbemClassObject:: BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="78c5f-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="78c5f-125">`lEnumFlags`引数として渡すことができるフラグは、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="78c5f-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="78c5f-126">各グループのフラグは、他のグループのフラグと組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="78c5f-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="78c5f-127">ただし、同じグループのフラグは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="78c5f-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="78c5f-128">**グループ1**</span><span class="sxs-lookup"><span data-stu-id="78c5f-128">**Group 1**</span></span>

|<span data-ttu-id="78c5f-129">定数</span><span class="sxs-lookup"><span data-stu-id="78c5f-129">Constant</span></span>  |<span data-ttu-id="78c5f-130">Value</span><span class="sxs-lookup"><span data-stu-id="78c5f-130">Value</span></span>  |<span data-ttu-id="78c5f-131">説明</span><span class="sxs-lookup"><span data-stu-id="78c5f-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="78c5f-132">0x4</span><span class="sxs-lookup"><span data-stu-id="78c5f-132">0x4</span></span> | <span data-ttu-id="78c5f-133">キーのみを構成するプロパティを含めます。</span><span class="sxs-lookup"><span data-stu-id="78c5f-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="78c5f-134">0x8</span><span class="sxs-lookup"><span data-stu-id="78c5f-134">0x8</span></span> | <span data-ttu-id="78c5f-135">オブジェクト参照のみのプロパティを含めます。</span><span class="sxs-lookup"><span data-stu-id="78c5f-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="78c5f-136">**グループ2**</span><span class="sxs-lookup"><span data-stu-id="78c5f-136">**Group 2**</span></span>

<span data-ttu-id="78c5f-137">定数</span><span class="sxs-lookup"><span data-stu-id="78c5f-137">Constant</span></span>  |<span data-ttu-id="78c5f-138">Value</span><span class="sxs-lookup"><span data-stu-id="78c5f-138">Value</span></span>  |<span data-ttu-id="78c5f-139">説明</span><span class="sxs-lookup"><span data-stu-id="78c5f-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="78c5f-140">0x30</span><span class="sxs-lookup"><span data-stu-id="78c5f-140">0x30</span></span> | <span data-ttu-id="78c5f-141">列挙体をシステムプロパティのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="78c5f-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="78c5f-142">0x40</span><span class="sxs-lookup"><span data-stu-id="78c5f-142">0x40</span></span> | <span data-ttu-id="78c5f-143">ローカルプロパティと伝達されたプロパティを含めますが、列挙からシステムプロパティを除外します。</span><span class="sxs-lookup"><span data-stu-id="78c5f-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="78c5f-144">クラスの場合:</span><span class="sxs-lookup"><span data-stu-id="78c5f-144">For classes:</span></span>

<span data-ttu-id="78c5f-145">定数</span><span class="sxs-lookup"><span data-stu-id="78c5f-145">Constant</span></span>  |<span data-ttu-id="78c5f-146">Value</span><span class="sxs-lookup"><span data-stu-id="78c5f-146">Value</span></span>  |<span data-ttu-id="78c5f-147">説明</span><span class="sxs-lookup"><span data-stu-id="78c5f-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="78c5f-148">0x100</span><span class="sxs-lookup"><span data-stu-id="78c5f-148">0x100</span></span> | <span data-ttu-id="78c5f-149">列挙型をクラス定義でオーバーライドされたプロパティに限定します。</span><span class="sxs-lookup"><span data-stu-id="78c5f-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="78c5f-150">0x100</span><span class="sxs-lookup"><span data-stu-id="78c5f-150">0x100</span></span> | <span data-ttu-id="78c5f-151">列挙体を、現在のクラス定義でオーバーライドされたプロパティと、クラスで定義されている新しいプロパティに限定します。</span><span class="sxs-lookup"><span data-stu-id="78c5f-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="78c5f-152">0x300</span><span class="sxs-lookup"><span data-stu-id="78c5f-152">0x300</span></span> | <span data-ttu-id="78c5f-153">`WBEM_FLAG_CLASS_OVERRIDES_ONLY` `lEnumFlags` また`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES`はが設定されているかどうかを確認するために、値に対して適用するマスク (フラグではなく)。</span><span class="sxs-lookup"><span data-stu-id="78c5f-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="78c5f-154">0x10</span><span class="sxs-lookup"><span data-stu-id="78c5f-154">0x10</span></span> | <span data-ttu-id="78c5f-155">列挙体は、クラス自体で定義または変更されたプロパティに限定します。</span><span class="sxs-lookup"><span data-stu-id="78c5f-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="78c5f-156">0x20</span><span class="sxs-lookup"><span data-stu-id="78c5f-156">0x20</span></span> | <span data-ttu-id="78c5f-157">列挙型を基底クラスから継承されたプロパティに限定します。</span><span class="sxs-lookup"><span data-stu-id="78c5f-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="78c5f-158">インスタンスの場合:</span><span class="sxs-lookup"><span data-stu-id="78c5f-158">For instances:</span></span>

<span data-ttu-id="78c5f-159">定数</span><span class="sxs-lookup"><span data-stu-id="78c5f-159">Constant</span></span>  |<span data-ttu-id="78c5f-160">Value</span><span class="sxs-lookup"><span data-stu-id="78c5f-160">Value</span></span>  |<span data-ttu-id="78c5f-161">説明</span><span class="sxs-lookup"><span data-stu-id="78c5f-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="78c5f-162">0x10</span><span class="sxs-lookup"><span data-stu-id="78c5f-162">0x10</span></span> | <span data-ttu-id="78c5f-163">列挙体は、クラス自体で定義または変更されたプロパティに限定します。</span><span class="sxs-lookup"><span data-stu-id="78c5f-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="78c5f-164">0x20</span><span class="sxs-lookup"><span data-stu-id="78c5f-164">0x20</span></span> | <span data-ttu-id="78c5f-165">列挙型を基底クラスから継承されたプロパティに限定します。</span><span class="sxs-lookup"><span data-stu-id="78c5f-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="78c5f-166">必要条件</span><span class="sxs-lookup"><span data-stu-id="78c5f-166">Requirements</span></span>  
 <span data-ttu-id="78c5f-167">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78c5f-167">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78c5f-168">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="78c5f-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="78c5f-169">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="78c5f-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78c5f-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="78c5f-170">See also</span></span>

- [<span data-ttu-id="78c5f-171">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="78c5f-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

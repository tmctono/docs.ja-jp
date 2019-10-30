---
title: Put 関数 (アンマネージ API リファレンス)
description: Put 関数は、名前付きプロパティに新しい値を割り当てます。
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f1bb8aa09a269e3b8fd23f393d63a275d308a77c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127403"
---
# <a name="put-function"></a><span data-ttu-id="836d7-103">Put 関数</span><span class="sxs-lookup"><span data-stu-id="836d7-103">Put function</span></span>

<span data-ttu-id="836d7-104">名前付きプロパティが新しい値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="836d7-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="836d7-105">構文</span><span class="sxs-lookup"><span data-stu-id="836d7-105">Syntax</span></span>

```cpp
HRESULT Put (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
);
```

## <a name="parameters"></a><span data-ttu-id="836d7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="836d7-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="836d7-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="836d7-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="836d7-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="836d7-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="836d7-109">からプロパティの名前。</span><span class="sxs-lookup"><span data-stu-id="836d7-109">[in] The name of the property.</span></span> <span data-ttu-id="836d7-110">このパラメーターを `null` とすることはできません。</span><span class="sxs-lookup"><span data-stu-id="836d7-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="836d7-111">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="836d7-111">[in] Reserved.</span></span> <span data-ttu-id="836d7-112">このパラメーターには0を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="836d7-112">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="836d7-113">から新しいプロパティ値になる有効な `VARIANT` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="836d7-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="836d7-114">`pVal` が `null` または `VT_NULL`型の `VARIANT` を指している場合、プロパティは `null`に設定されます。</span><span class="sxs-lookup"><span data-stu-id="836d7-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span>

`vtType`\
<span data-ttu-id="836d7-115">から`pVal`によってポイントされている `VARIANT` の型。</span><span class="sxs-lookup"><span data-stu-id="836d7-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="836d7-116">詳細については、「[解説](#remarks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="836d7-116">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="836d7-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="836d7-117">Return value</span></span>

<span data-ttu-id="836d7-118">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="836d7-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="836d7-119">定数</span><span class="sxs-lookup"><span data-stu-id="836d7-119">Constant</span></span>  |<span data-ttu-id="836d7-120">[値]</span><span class="sxs-lookup"><span data-stu-id="836d7-120">Value</span></span>  |<span data-ttu-id="836d7-121">説明</span><span class="sxs-lookup"><span data-stu-id="836d7-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="836d7-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="836d7-122">0x80041001</span></span> | <span data-ttu-id="836d7-123">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="836d7-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="836d7-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="836d7-124">0x80041008</span></span> | <span data-ttu-id="836d7-125">1つ以上のパラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="836d7-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="836d7-126">0x80041024</span><span class="sxs-lookup"><span data-stu-id="836d7-126">0x8004102a</span></span> | <span data-ttu-id="836d7-127">プロパティの型が認識されません。</span><span class="sxs-lookup"><span data-stu-id="836d7-127">The property type is not recognized.</span></span> <span data-ttu-id="836d7-128">この値は、クラスが既に存在する場合に、クラスのインスタンスを作成するときに返されます。</span><span class="sxs-lookup"><span data-stu-id="836d7-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="836d7-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="836d7-129">0x80041006</span></span> | <span data-ttu-id="836d7-130">操作を完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="836d7-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="836d7-131">0x80041005</span><span class="sxs-lookup"><span data-stu-id="836d7-131">0x80041005</span></span> | <span data-ttu-id="836d7-132">インスタンスの場合: `pVal` が、プロパティに対して正しくない型の `VARIANT` を指していることを示します。</span><span class="sxs-lookup"><span data-stu-id="836d7-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="836d7-133">クラス定義の場合: プロパティは既に親クラスに存在し、新しい COM 型は古い COM 型とは異なります。</span><span class="sxs-lookup"><span data-stu-id="836d7-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="836d7-134">0</span><span class="sxs-lookup"><span data-stu-id="836d7-134">0</span></span> | <span data-ttu-id="836d7-135">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="836d7-135">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="836d7-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="836d7-136">Remarks</span></span>

<span data-ttu-id="836d7-137">この関数は、 [IWbemClassObject::P ut](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="836d7-137">This function wraps a call to the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

<span data-ttu-id="836d7-138">この関数は、常に現在のプロパティ値を新しい値で上書きします。</span><span class="sxs-lookup"><span data-stu-id="836d7-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="836d7-139">[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)がクラス定義を指している場合は、`Put` によってプロパティ値が作成または更新されます。</span><span class="sxs-lookup"><span data-stu-id="836d7-139">If the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="836d7-140">[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)が CIM インスタンスをポイントすると、`Put` はプロパティ値のみを更新します。プロパティ値を作成 `Put` ことはできません。</span><span class="sxs-lookup"><span data-stu-id="836d7-140">When [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="836d7-141">`__CLASS` システムプロパティは、クラスの作成時に、空白のままにできない場合にのみ書き込み可能です。</span><span class="sxs-lookup"><span data-stu-id="836d7-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="836d7-142">その他のすべてのシステムプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="836d7-142">All other system properties are read-only.</span></span>

<span data-ttu-id="836d7-143">ユーザーは、アンダースコア ("_") で始まる名前のプロパティを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="836d7-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="836d7-144">これは、システムクラスおよびプロパティ用に予約されています。</span><span class="sxs-lookup"><span data-stu-id="836d7-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="836d7-145">`Put` 関数によって設定されたプロパティが親クラスに存在する場合、プロパティの型が親クラスの型と一致しない限り、プロパティの既定値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="836d7-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="836d7-146">プロパティが存在せず、型が一致しない場合は、プロパティが作成されます。</span><span class="sxs-lookup"><span data-stu-id="836d7-146">If the property does not exist and it is not a type mismatch, the property is created.</span></span>

<span data-ttu-id="836d7-147">`vtType` パラメーターは、CIM クラス定義で新しいプロパティを作成する場合にのみ使用し、`pVal` は `null` または `VT_NULL`型の `VARIANT` を指します。</span><span class="sxs-lookup"><span data-stu-id="836d7-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="836d7-148">この場合、`vType` パラメーターによって、プロパティの CIM 型が指定されます。</span><span class="sxs-lookup"><span data-stu-id="836d7-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="836d7-149">それ以外の場合は、`vtType` を0にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="836d7-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="836d7-150">プロパティの型が固定され、変更できないため、基になるオブジェクトがインスタンスの場合 (`Val` が `null`の場合でも)、`vtType` も0にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="836d7-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>

## <a name="example"></a><span data-ttu-id="836d7-151">例</span><span class="sxs-lookup"><span data-stu-id="836d7-151">Example</span></span>

<span data-ttu-id="836d7-152">例については、「 [IWbemClassObject::P ut](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put)メソッド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="836d7-152">For an example, see the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="836d7-153">［要件］</span><span class="sxs-lookup"><span data-stu-id="836d7-153">Requirements</span></span>

<span data-ttu-id="836d7-154">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="836d7-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="836d7-155">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="836d7-155">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="836d7-156">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="836d7-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="836d7-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="836d7-157">See also</span></span>

- [<span data-ttu-id="836d7-158">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="836d7-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

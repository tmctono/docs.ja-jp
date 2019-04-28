---
title: Get 関数 (アンマネージ API リファレンス)
description: Get 関数には、指定されたプロパティ値を取得します。
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7534d760f902f80d42c6c20c57a34d52012997a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608997"
---
# <a name="get-function"></a><span data-ttu-id="ae88f-103">Get 関数</span><span class="sxs-lookup"><span data-stu-id="ae88f-103">Get function</span></span>

<span data-ttu-id="ae88f-104">存在する場合は、指定されたプロパティ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="ae88f-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ae88f-105">構文</span><span class="sxs-lookup"><span data-stu-id="ae88f-105">Syntax</span></span>

```
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```

## <a name="parameters"></a><span data-ttu-id="ae88f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ae88f-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="ae88f-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="ae88f-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="ae88f-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="ae88f-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="ae88f-109">[in]プロパティの名前。</span><span class="sxs-lookup"><span data-stu-id="ae88f-109">[in] The name of the property.</span></span>

`lFlags`\
<span data-ttu-id="ae88f-110">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="ae88f-110">[in] Reserved.</span></span> <span data-ttu-id="ae88f-111">このパラメーターは、0 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae88f-111">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="ae88f-112">[out]関数が正常に返された場合の値が含まれています、`wszName`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ae88f-112">[out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="ae88f-113">`pval`引数には、正しい型および修飾子の値が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="ae88f-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

`pvtType`\
<span data-ttu-id="ae88f-114">[out]関数が正常に返された場合は、 [CIM 型の定数](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration)プロパティの型を示します。</span><span class="sxs-lookup"><span data-stu-id="ae88f-114">[out] If the function returns successfully, contains a [CIM-type constant](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="ae88f-115">その値が指定できますも`null`します。</span><span class="sxs-lookup"><span data-stu-id="ae88f-115">Its value can also be `null`.</span></span> 

`plFlavor`\
<span data-ttu-id="ae88f-116">[out]関数が正常に返された場合は、プロパティのパブリッシュ元に関する情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ae88f-116">[out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="ae88f-117">その値を指定できます`null`、またはいずれかで定義されている次の WBEM_FLAVOR_TYPE 定数、 *WbemCli.h*ヘッダー ファイル。</span><span class="sxs-lookup"><span data-stu-id="ae88f-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span> 

|<span data-ttu-id="ae88f-118">定数</span><span class="sxs-lookup"><span data-stu-id="ae88f-118">Constant</span></span>  |<span data-ttu-id="ae88f-119">値</span><span class="sxs-lookup"><span data-stu-id="ae88f-119">Value</span></span>  |<span data-ttu-id="ae88f-120">説明</span><span class="sxs-lookup"><span data-stu-id="ae88f-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="ae88f-121">0x40</span><span class="sxs-lookup"><span data-stu-id="ae88f-121">0x40</span></span> | <span data-ttu-id="ae88f-122">プロパティは、標準のシステム プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ae88f-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="ae88f-123">0x20</span><span class="sxs-lookup"><span data-stu-id="ae88f-123">0x20</span></span> | <span data-ttu-id="ae88f-124">クラス。プロパティは、親クラスから継承されます。</span><span class="sxs-lookup"><span data-stu-id="ae88f-124">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="ae88f-125">インスタンス。プロパティを親クラスから継承したときに変更されていないインスタンスがします。</span><span class="sxs-lookup"><span data-stu-id="ae88f-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="ae88f-126">0</span><span class="sxs-lookup"><span data-stu-id="ae88f-126">0</span></span> | <span data-ttu-id="ae88f-127">クラス。プロパティは、派生クラスに属しています。</span><span class="sxs-lookup"><span data-stu-id="ae88f-127">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="ae88f-128">インスタンス。インスタンスでプロパティを変更します。つまり、値が指定されましたまたは修飾子が追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="ae88f-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="ae88f-129">戻り値</span><span class="sxs-lookup"><span data-stu-id="ae88f-129">Return value</span></span>

<span data-ttu-id="ae88f-130">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="ae88f-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ae88f-131">定数</span><span class="sxs-lookup"><span data-stu-id="ae88f-131">Constant</span></span>  |<span data-ttu-id="ae88f-132">値</span><span class="sxs-lookup"><span data-stu-id="ae88f-132">Value</span></span>  |<span data-ttu-id="ae88f-133">説明</span><span class="sxs-lookup"><span data-stu-id="ae88f-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="ae88f-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ae88f-134">0x80041001</span></span> | <span data-ttu-id="ae88f-135">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ae88f-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ae88f-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ae88f-136">0x80041008</span></span> | <span data-ttu-id="ae88f-137">1 つまたは複数のパラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="ae88f-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="ae88f-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="ae88f-138">0x80041002</span></span> | <span data-ttu-id="ae88f-139">指定したプロパティが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="ae88f-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ae88f-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ae88f-140">0x80041006</span></span> | <span data-ttu-id="ae88f-141">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="ae88f-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ae88f-142">0</span><span class="sxs-lookup"><span data-stu-id="ae88f-142">0</span></span> | <span data-ttu-id="ae88f-143">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="ae88f-143">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="ae88f-144">Remarks</span><span class="sxs-lookup"><span data-stu-id="ae88f-144">Remarks</span></span>

<span data-ttu-id="ae88f-145">この関数の呼び出しをラップする、 [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get)メソッド。</span><span class="sxs-lookup"><span data-stu-id="ae88f-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="ae88f-146">`Get`関数では、システムのプロパティを返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="ae88f-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="ae88f-147">`pVal`引数には、正しい型および修飾子と COM の値が割り当てられている[VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit)関数</span><span class="sxs-lookup"><span data-stu-id="ae88f-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="ae88f-148">必要条件</span><span class="sxs-lookup"><span data-stu-id="ae88f-148">Requirements</span></span>

 <span data-ttu-id="ae88f-149">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae88f-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="ae88f-150">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ae88f-150">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="ae88f-151">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ae88f-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ae88f-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae88f-152">See also</span></span>

- [<span data-ttu-id="ae88f-153">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="ae88f-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
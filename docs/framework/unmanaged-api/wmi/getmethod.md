---
title: GetMethod 関数 (アンマネージ API リファレンス)
description: GetMethod 関数は、メソッドに関する情報を取得します。
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9cc185bf8cccb8ed3c24e28954afd86464602d7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798567"
---
# <a name="getmethod-function"></a><span data-ttu-id="42627-103">GetMethod 関数</span><span class="sxs-lookup"><span data-stu-id="42627-103">GetMethod function</span></span>

<span data-ttu-id="42627-104">指定したメソッドに関する情報が取得されます。</span><span class="sxs-lookup"><span data-stu-id="42627-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="42627-105">構文</span><span class="sxs-lookup"><span data-stu-id="42627-105">Syntax</span></span>

```cpp
HRESULT GetMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```

## <a name="parameters"></a><span data-ttu-id="42627-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42627-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="42627-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="42627-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="42627-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="42627-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="42627-109">からメソッド名。</span><span class="sxs-lookup"><span data-stu-id="42627-109">[in] The method name.</span></span> <span data-ttu-id="42627-110">このパラメーターをに`null`することはできません`LPCWSTR`。また、有効なを指す必要があります。</span><span class="sxs-lookup"><span data-stu-id="42627-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`\
<span data-ttu-id="42627-111">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="42627-111">[in] Reserved.</span></span> <span data-ttu-id="42627-112">このパラメーターには0を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42627-112">This parameter must be 0.</span></span>

`ppInSignature`\
<span data-ttu-id="42627-113">入出力メソッドの in パラメーターを記述する[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="42627-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in parameters to the method.</span></span> <span data-ttu-id="42627-114">に`null`設定されている場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="42627-114">This parameter is ignored if it is set to `null`.</span></span>

`ppOutSignature`\
<span data-ttu-id="42627-115">入出力メソッドの出力パラメーターを記述する[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="42627-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="42627-116">に`null`設定されている場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="42627-116">This parameter is ignored if it is set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="42627-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="42627-117">Return value</span></span>

<span data-ttu-id="42627-118">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="42627-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="42627-119">定数</span><span class="sxs-lookup"><span data-stu-id="42627-119">Constant</span></span>  |<span data-ttu-id="42627-120">Value</span><span class="sxs-lookup"><span data-stu-id="42627-120">Value</span></span>  |<span data-ttu-id="42627-121">説明</span><span class="sxs-lookup"><span data-stu-id="42627-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="42627-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="42627-122">0x80041002</span></span> | <span data-ttu-id="42627-123">指定されたプロパティが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="42627-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="42627-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="42627-124">0x80041006</span></span> | <span data-ttu-id="42627-125">操作を完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="42627-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="42627-126">0</span><span class="sxs-lookup"><span data-stu-id="42627-126">0</span></span> | <span data-ttu-id="42627-127">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="42627-127">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="42627-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="42627-128">Remarks</span></span>

<span data-ttu-id="42627-129">この関数は、 [IWbemClassObject:: GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="42627-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="42627-130">メソッドに in パラメーターがない場合、 `null` Windows Management は [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ポインターをに設定できます。</span><span class="sxs-lookup"><span data-stu-id="42627-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="42627-131">で`ppInSignature`は`ppOutSignature` 、とはそれぞれ、システムクラス[パラメーター](/windows/desktop/WmiSdk/--parameters)の`IWbemClassObject`インスタンスのプロパティとして in および out パラメーターを記述します。</span><span class="sxs-lookup"><span data-stu-id="42627-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="42627-132">`ppInSignature`のプロパティには*n*という名前が付け`Param`られます。ここで、 *n*はメソッドシグネチャ内`Param1`の`Param2`パラメーターの位置 (、など) です。</span><span class="sxs-lookup"><span data-stu-id="42627-132">The properties in `ppInSignature` are named `Param`*n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="42627-133">の`ppOutSignature`プロパティにも*n*と`Param`いう名前が付けられ、戻り`ReturnValue`値はという名前になります。</span><span class="sxs-lookup"><span data-stu-id="42627-133">The properties in `ppOutSignature` are also named `Param`*n*, and the return value is named `ReturnValue`.</span></span> <span data-ttu-id="42627-134">詳細と例については、「 [IWbemClassObject:: GetMethod メソッド](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42627-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="42627-135">必要条件</span><span class="sxs-lookup"><span data-stu-id="42627-135">Requirements</span></span>

<span data-ttu-id="42627-136">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42627-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="42627-137">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="42627-137">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="42627-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="42627-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="42627-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="42627-139">See also</span></span>

- [<span data-ttu-id="42627-140">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="42627-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

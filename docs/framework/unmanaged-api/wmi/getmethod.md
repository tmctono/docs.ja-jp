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
ms.openlocfilehash: 48986f5ff1cbbb45840ec1a059aa86711848d717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102591"
---
# <a name="getmethod-function"></a><span data-ttu-id="282cd-103">GetMethod 関数</span><span class="sxs-lookup"><span data-stu-id="282cd-103">GetMethod function</span></span>

<span data-ttu-id="282cd-104">指定したメソッドに関する情報が取得されます。</span><span class="sxs-lookup"><span data-stu-id="282cd-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="282cd-105">構文</span><span class="sxs-lookup"><span data-stu-id="282cd-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="282cd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="282cd-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="282cd-107">からこのパラメーターは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="282cd-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="282cd-108">から[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="282cd-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="282cd-109">からメソッド名。</span><span class="sxs-lookup"><span data-stu-id="282cd-109">[in] The method name.</span></span> <span data-ttu-id="282cd-110">このパラメーターは `null` できず、有効な `LPCWSTR`を指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="282cd-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`\
<span data-ttu-id="282cd-111">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="282cd-111">[in] Reserved.</span></span> <span data-ttu-id="282cd-112">このパラメーターには0を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="282cd-112">This parameter must be 0.</span></span>

`ppInSignature`\
<span data-ttu-id="282cd-113">入出力メソッドの in パラメーターを記述する[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="282cd-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in parameters to the method.</span></span> <span data-ttu-id="282cd-114">`null`に設定されている場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="282cd-114">This parameter is ignored if it is set to `null`.</span></span>

`ppOutSignature`\
<span data-ttu-id="282cd-115">入出力メソッドの出力パラメーターを記述する[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="282cd-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="282cd-116">`null`に設定されている場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="282cd-116">This parameter is ignored if it is set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="282cd-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="282cd-117">Return value</span></span>

<span data-ttu-id="282cd-118">この関数によって返される次の値は、 *WbemCli*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="282cd-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="282cd-119">定数</span><span class="sxs-lookup"><span data-stu-id="282cd-119">Constant</span></span>  |<span data-ttu-id="282cd-120">[値]</span><span class="sxs-lookup"><span data-stu-id="282cd-120">Value</span></span>  |<span data-ttu-id="282cd-121">説明</span><span class="sxs-lookup"><span data-stu-id="282cd-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="282cd-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="282cd-122">0x80041002</span></span> | <span data-ttu-id="282cd-123">指定されたプロパティが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="282cd-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="282cd-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="282cd-124">0x80041006</span></span> | <span data-ttu-id="282cd-125">操作を完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="282cd-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="282cd-126">0</span><span class="sxs-lookup"><span data-stu-id="282cd-126">0</span></span> | <span data-ttu-id="282cd-127">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="282cd-127">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="282cd-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="282cd-128">Remarks</span></span>

<span data-ttu-id="282cd-129">この関数は、 [IWbemClassObject:: GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)メソッドの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="282cd-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="282cd-130">メソッドに in パラメーターがない場合、Windows Management は[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)ポインターを `null` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="282cd-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="282cd-131">`ppInSignature` と `ppOutSignature` では、それぞれ in パラメーターと out パラメーターを、システムクラス[パラメーター](/windows/desktop/WmiSdk/--parameters)の `IWbemClassObject` インスタンスのプロパティとして記述します。</span><span class="sxs-lookup"><span data-stu-id="282cd-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="282cd-132">`ppInSignature` のプロパティの名前は `Param`*n*です。ここで、 *n*はメソッドシグネチャ内のパラメーターの位置 (`Param1`、`Param2`など) です。</span><span class="sxs-lookup"><span data-stu-id="282cd-132">The properties in `ppInSignature` are named `Param`*n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="282cd-133">`ppOutSignature` のプロパティも `Param`*n*という名前で、戻り値の名前は `ReturnValue`です。</span><span class="sxs-lookup"><span data-stu-id="282cd-133">The properties in `ppOutSignature` are also named `Param`*n*, and the return value is named `ReturnValue`.</span></span> <span data-ttu-id="282cd-134">詳細と例については、「 [IWbemClassObject:: GetMethod メソッド](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="282cd-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="282cd-135">［要件］</span><span class="sxs-lookup"><span data-stu-id="282cd-135">Requirements</span></span>

<span data-ttu-id="282cd-136">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="282cd-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="282cd-137">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="282cd-137">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="282cd-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="282cd-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="282cd-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="282cd-139">See also</span></span>

- [<span data-ttu-id="282cd-140">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="282cd-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

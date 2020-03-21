---
title: QualifierSet_Get関数 (アンマネージ API リファレンス)
description: QualifierSet_Get関数は、名前付き修飾子を取得します。
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 2f4e2d4518e01f3415b8f17ce5778dd98b2a45c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174889"
---
# <a name="qualifierset_get-function"></a><span data-ttu-id="bf49e-103">QualifierSet_Get 関数</span><span class="sxs-lookup"><span data-stu-id="bf49e-103">QualifierSet_Get function</span></span>
<span data-ttu-id="bf49e-104">指定した名前付き修飾子が取得されます。</span><span class="sxs-lookup"><span data-stu-id="bf49e-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bf49e-105">構文</span><span class="sxs-lookup"><span data-stu-id="bf49e-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a><span data-ttu-id="bf49e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf49e-106">Parameters</span></span>

<span data-ttu-id="bf49e-107">`vFunc`[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="bf49e-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="bf49e-108">`ptr`[in][インスタンス](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bf49e-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="bf49e-109">`wszName`[in]値が要求された修飾子の名前。</span><span class="sxs-lookup"><span data-stu-id="bf49e-109">`wszName` [in] The name of the qualifier whose value is requested.</span></span>

<span data-ttu-id="bf49e-110">`lFlags`[in]予約。</span><span class="sxs-lookup"><span data-stu-id="bf49e-110">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="bf49e-111">このパラメーターは 0 でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="bf49e-111">This parameter must be 0.</span></span>

<span data-ttu-id="bf49e-112">`pVal`[アウト]成功した場合は、修飾子の正しい型と値。</span><span class="sxs-lookup"><span data-stu-id="bf49e-112">`pVal` [out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="bf49e-113">関数が失敗した場合、`VARIANT`指すが`pVal`変更されません。</span><span class="sxs-lookup"><span data-stu-id="bf49e-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="bf49e-114">このパラメーターが`null`の場合、パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="bf49e-114">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="bf49e-115">`plFlavor`[アウト]要求された修飾子の修飾子フレーバー ビットを受け取る LONG へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bf49e-115">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="bf49e-116">フレーバー情報が必要ない場合、このパラメーターは`null`.</span><span class="sxs-lookup"><span data-stu-id="bf49e-116">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="bf49e-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="bf49e-117">Return value</span></span>

<span data-ttu-id="bf49e-118">この関数によって返される次の値は *、WbemCli.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="bf49e-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bf49e-119">常時</span><span class="sxs-lookup"><span data-stu-id="bf49e-119">Constant</span></span>  |<span data-ttu-id="bf49e-120">Value</span><span class="sxs-lookup"><span data-stu-id="bf49e-120">Value</span></span>  |<span data-ttu-id="bf49e-121">説明</span><span class="sxs-lookup"><span data-stu-id="bf49e-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bf49e-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bf49e-122">0x80041008</span></span> | <span data-ttu-id="bf49e-123">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="bf49e-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="bf49e-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="bf49e-124">0x80041002</span></span> | <span data-ttu-id="bf49e-125">指定された修飾子が存在しません。</span><span class="sxs-lookup"><span data-stu-id="bf49e-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="bf49e-126">0</span><span class="sxs-lookup"><span data-stu-id="bf49e-126">0</span></span> | <span data-ttu-id="bf49e-127">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="bf49e-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="bf49e-128">解説</span><span class="sxs-lookup"><span data-stu-id="bf49e-128">Remarks</span></span>

<span data-ttu-id="bf49e-129">この関数は[、IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get)メソッドへの呼び出しをラップします。</span><span class="sxs-lookup"><span data-stu-id="bf49e-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf49e-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="bf49e-130">Requirements</span></span>  
 <span data-ttu-id="bf49e-131">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf49e-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf49e-132">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bf49e-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bf49e-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bf49e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf49e-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf49e-134">See also</span></span>

- [<span data-ttu-id="bf49e-135">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="bf49e-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

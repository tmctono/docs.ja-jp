---
title: BlessIWbemServicesObject 関数 (アンマネージ API リファレンス)
description: BlessIWbemServicesObject 関数では、ユーザーの資格情報が [iwbemservices] オブジェクトへのアクセスを許可するかどうかを示します
ms.date: 11/06/2017
api_name:
- BlessIWbemServicesObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServicesObject
helpviewer_keywords:
- BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d28497c637a40d7e2659b18868124ea898397f92
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636909"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="3d340-103">BlessIWbemServicesObject 関数</span><span class="sxs-lookup"><span data-stu-id="3d340-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="3d340-104">ユーザーの資格情報が、指定されたアクセスを許可するかどうかを示す[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3d340-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="3d340-105">構文</span><span class="sxs-lookup"><span data-stu-id="3d340-105">Syntax</span></span>

```
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a><span data-ttu-id="3d340-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3d340-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="3d340-107">[in]WMI サービス オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3d340-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="3d340-108">[in]ユーザー名。</span><span class="sxs-lookup"><span data-stu-id="3d340-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="3d340-109">[in]関連付けられているパスワード`strUser`します。</span><span class="sxs-lookup"><span data-stu-id="3d340-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="3d340-110">[in]ユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="3d340-110">[in] The domain name of the user.</span></span> <span data-ttu-id="3d340-111">参照してください、 [ConnectServerWmi](connectserverwmi.md)関数の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="3d340-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="3d340-112">[in]偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="3d340-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="3d340-113">[in]承認レベル。</span><span class="sxs-lookup"><span data-stu-id="3d340-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="3d340-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="3d340-114">Return value</span></span>

<span data-ttu-id="3d340-115">この関数によって返される次の値が定義されている、 *WinError.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="3d340-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3d340-116">定数</span><span class="sxs-lookup"><span data-stu-id="3d340-116">Constant</span></span>  |<span data-ttu-id="3d340-117">値</span><span class="sxs-lookup"><span data-stu-id="3d340-117">Value</span></span>  |<span data-ttu-id="3d340-118">説明</span><span class="sxs-lookup"><span data-stu-id="3d340-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="3d340-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="3d340-119">0x80070057</span></span> | <span data-ttu-id="3d340-120">1 つまたは複数の引数が無効です。</span><span class="sxs-lookup"><span data-stu-id="3d340-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="3d340-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="3d340-121">0x80004003</span></span> | <span data-ttu-id="3d340-122">`pIWbemServices` は `null` です。</span><span class="sxs-lookup"><span data-stu-id="3d340-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="3d340-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="3d340-123">0x80000008</span></span> | <span data-ttu-id="3d340-124">不明なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3d340-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="3d340-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="3d340-125">0x80000002</span></span> | <span data-ttu-id="3d340-126">メモリ不足のためでは、操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d340-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="3d340-127">0</span><span class="sxs-lookup"><span data-stu-id="3d340-127">0</span></span> | <span data-ttu-id="3d340-128">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="3d340-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="3d340-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="3d340-129">Requirements</span></span>

 <span data-ttu-id="3d340-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d340-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="3d340-131">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3d340-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="3d340-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3d340-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3d340-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d340-133">See also</span></span>

- [<span data-ttu-id="3d340-134">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3d340-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

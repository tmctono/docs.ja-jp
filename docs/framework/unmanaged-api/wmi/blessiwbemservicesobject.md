---
title: 関数 (アンマネージ API リファレンス)
description: 関数は、ユーザー資格情報が IWbemServices オブジェクトへのアクセスを許可するかどうかを示します。
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
ms.openlocfilehash: fd822f78d29ad3a75fb5e57dd7c23b7049d445b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175032"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="04d98-103">BlessIWbemServicesObject 関数</span><span class="sxs-lookup"><span data-stu-id="04d98-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="04d98-104">指定された[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)オブジェクトへのアクセスをユーザー資格情報で許可するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="04d98-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="04d98-105">構文</span><span class="sxs-lookup"><span data-stu-id="04d98-105">Syntax</span></span>

```cpp
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a><span data-ttu-id="04d98-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04d98-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="04d98-107">[in]WMI サービス オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="04d98-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="04d98-108">[in]ユーザー名。</span><span class="sxs-lookup"><span data-stu-id="04d98-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="04d98-109">[in]に関連付けられている`strUser`パスワード。</span><span class="sxs-lookup"><span data-stu-id="04d98-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="04d98-110">[in]ユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="04d98-110">[in] The domain name of the user.</span></span> <span data-ttu-id="04d98-111">詳細については、[関数](connectserverwmi.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04d98-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="04d98-112">[in]偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="04d98-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="04d98-113">[in]権限レベル。</span><span class="sxs-lookup"><span data-stu-id="04d98-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="04d98-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="04d98-114">Return value</span></span>

<span data-ttu-id="04d98-115">この関数によって返される次の値は *、WinError.h*ヘッダー ファイルで定義されているか、コード内で定数として定義できます。</span><span class="sxs-lookup"><span data-stu-id="04d98-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="04d98-116">常時</span><span class="sxs-lookup"><span data-stu-id="04d98-116">Constant</span></span>  |<span data-ttu-id="04d98-117">Value</span><span class="sxs-lookup"><span data-stu-id="04d98-117">Value</span></span>  |<span data-ttu-id="04d98-118">説明</span><span class="sxs-lookup"><span data-stu-id="04d98-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="04d98-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="04d98-119">0x80070057</span></span> | <span data-ttu-id="04d98-120">1 つ以上の引数が無効です。</span><span class="sxs-lookup"><span data-stu-id="04d98-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="04d98-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="04d98-121">0x80004003</span></span> | <span data-ttu-id="04d98-122">`pIWbemServices` は `null` です。</span><span class="sxs-lookup"><span data-stu-id="04d98-122">`pIWbemServices` is `null`.</span></span> |
| `E_FAIL` | <span data-ttu-id="04d98-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="04d98-123">0x80000008</span></span> | <span data-ttu-id="04d98-124">特定できないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="04d98-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="04d98-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="04d98-125">0x80000002</span></span> | <span data-ttu-id="04d98-126">メモリ不足のため、操作を実行できません。</span><span class="sxs-lookup"><span data-stu-id="04d98-126">Insufficient memory is available to perform the operation.</span></span> |
| `S_OK` | <span data-ttu-id="04d98-127">0</span><span class="sxs-lookup"><span data-stu-id="04d98-127">0</span></span> | <span data-ttu-id="04d98-128">関数呼び出しが正常に行われました。</span><span class="sxs-lookup"><span data-stu-id="04d98-128">The function call was successful.</span></span> |

## <a name="requirements"></a><span data-ttu-id="04d98-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="04d98-129">Requirements</span></span>

 <span data-ttu-id="04d98-130">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04d98-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="04d98-131">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="04d98-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="04d98-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="04d98-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="04d98-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="04d98-133">See also</span></span>

- [<span data-ttu-id="04d98-134">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="04d98-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

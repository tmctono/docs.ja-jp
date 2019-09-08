---
title: BlessIWbemServices 関数 (アンマネージ API リファレンス)
description: BlessIWbemServices 関数は、ユーザー資格情報が IWbemServices クラスへのアクセスを許可しているかどうかを示します。
ms.date: 11/06/2017
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57ab5eb418b5f0a9175074c87837c7cac8936346
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799043"
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="2bf29-103">BlessIWbemServices 関数</span><span class="sxs-lookup"><span data-stu-id="2bf29-103">BlessIWbemServices function</span></span>
<span data-ttu-id="2bf29-104">ユーザー資格情報が、指定された[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)クラスへのアクセスを許可するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2bf29-104">Indicates whether the user credentials permit access to the specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) class.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2bf29-105">構文</span><span class="sxs-lookup"><span data-stu-id="2bf29-105">Syntax</span></span>  
  
```  
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="2bf29-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2bf29-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="2bf29-107">から権限が必要な[IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2bf29-107">[in] A pointer to the [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object for which permissions are required.</span></span>

`strUser`\
<span data-ttu-id="2bf29-108">からユーザー名。</span><span class="sxs-lookup"><span data-stu-id="2bf29-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="2bf29-109">からに`strUser`関連付けられているパスワード。</span><span class="sxs-lookup"><span data-stu-id="2bf29-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="2bf29-110">からユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="2bf29-110">[in] The domain name of the user.</span></span> <span data-ttu-id="2bf29-111">詳細については、「 [Connectserverwmi](connectserverwmi.md)関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bf29-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="2bf29-112">から偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="2bf29-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="2bf29-113">から承認レベル。</span><span class="sxs-lookup"><span data-stu-id="2bf29-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="2bf29-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="2bf29-114">Return value</span></span>

<span data-ttu-id="2bf29-115">この関数によって返される次の値は、 *winerror.h*ヘッダーファイルで定義されています。また、コード内で定数として定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="2bf29-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2bf29-116">定数</span><span class="sxs-lookup"><span data-stu-id="2bf29-116">Constant</span></span>  |<span data-ttu-id="2bf29-117">Value</span><span class="sxs-lookup"><span data-stu-id="2bf29-117">Value</span></span>  |<span data-ttu-id="2bf29-118">説明</span><span class="sxs-lookup"><span data-stu-id="2bf29-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="2bf29-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="2bf29-119">0x80070057</span></span> | <span data-ttu-id="2bf29-120">1つ以上の引数が無効です。</span><span class="sxs-lookup"><span data-stu-id="2bf29-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="2bf29-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="2bf29-121">0x80004003</span></span> | <span data-ttu-id="2bf29-122">`pIWbemServices` は `null` です。</span><span class="sxs-lookup"><span data-stu-id="2bf29-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="2bf29-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="2bf29-123">0x80000008</span></span> | <span data-ttu-id="2bf29-124">特定できないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2bf29-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="2bf29-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="2bf29-125">0x80000002</span></span> | <span data-ttu-id="2bf29-126">操作を実行するのに十分なメモリがありません。</span><span class="sxs-lookup"><span data-stu-id="2bf29-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="2bf29-127">0</span><span class="sxs-lookup"><span data-stu-id="2bf29-127">0</span></span> | <span data-ttu-id="2bf29-128">関数の呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="2bf29-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="2bf29-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="2bf29-129">Requirements</span></span>  

 <span data-ttu-id="2bf29-130">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bf29-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bf29-131">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="2bf29-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2bf29-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2bf29-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bf29-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bf29-133">See also</span></span>

- [<span data-ttu-id="2bf29-134">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="2bf29-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

---
title: LoadStringRCEx 関数
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
ms.openlocfilehash: a300c2679ef11a84edb2ab89c8dea96e445c9ee3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177982"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="3a3a4-102">LoadStringRCEx 関数</span><span class="sxs-lookup"><span data-stu-id="3a3a4-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="3a3a4-103">HRESULT 値を、指定したカルチャの適切なエラー メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="3a3a4-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="3a3a4-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="3a3a4-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a3a4-105">構文</span><span class="sxs-lookup"><span data-stu-id="3a3a4-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a3a4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a3a4-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="3a3a4-107">[in]カルチャ識別子。</span><span class="sxs-lookup"><span data-stu-id="3a3a4-107">[in] A culture identifier.</span></span> <span data-ttu-id="3a3a4-108">既定のカルチャを`lcid`使用するには、-1 を渡します。</span><span class="sxs-lookup"><span data-stu-id="3a3a4-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="3a3a4-109">[in]HRESULT。</span><span class="sxs-lookup"><span data-stu-id="3a3a4-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="3a3a4-110">[アウト]正常終了時にエラー メッセージが格納されているバッファー。</span><span class="sxs-lookup"><span data-stu-id="3a3a4-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="3a3a4-111">[in]エラー メッセージ バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="3a3a4-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="3a3a4-112">[in]無視。</span><span class="sxs-lookup"><span data-stu-id="3a3a4-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="3a3a4-113">[アウト]エラー メッセージの長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3a3a4-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a3a4-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="3a3a4-114">Return Value</span></span>  
 <span data-ttu-id="3a3a4-115">このメソッドは、WinError.h で定義されている標準 COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="3a3a4-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="3a3a4-116">リターン コード</span><span class="sxs-lookup"><span data-stu-id="3a3a4-116">Return code</span></span>|<span data-ttu-id="3a3a4-117">説明</span><span class="sxs-lookup"><span data-stu-id="3a3a4-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3a3a4-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a3a4-118">S_OK</span></span>|<span data-ttu-id="3a3a4-119">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="3a3a4-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="3a3a4-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3a3a4-120">E_INVALIDARG</span></span>|<span data-ttu-id="3a3a4-121">`szBuffer`は null`iMax`であるか、ゼロ (0) です。</span><span class="sxs-lookup"><span data-stu-id="3a3a4-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a3a4-122">解説</span><span class="sxs-lookup"><span data-stu-id="3a3a4-122">Remarks</span></span>  
 <span data-ttu-id="3a3a4-123">メソッドが正常に完了しなかった場合は、`szBuffer`空の文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3a3a4-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a3a4-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="3a3a4-124">Requirements</span></span>  
 <span data-ttu-id="3a3a4-125">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a3a4-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a3a4-126">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3a3a4-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3a3a4-127">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a3a4-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a3a4-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a3a4-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a3a4-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a3a4-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3a3a4-130">LoadStringRC 関数</span><span class="sxs-lookup"><span data-stu-id="3a3a4-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="3a3a4-131">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="3a3a4-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

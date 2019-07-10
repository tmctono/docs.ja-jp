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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a0cac77d7bf7611acf6042298bfe6814d8f4352
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768454"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="c1e33-102">LoadStringRCEx 関数</span><span class="sxs-lookup"><span data-stu-id="c1e33-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="c1e33-103">HRESULT 値を、指定したカルチャの適切なエラー メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="c1e33-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="c1e33-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c1e33-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1e33-105">構文</span><span class="sxs-lookup"><span data-stu-id="c1e33-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c1e33-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c1e33-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="c1e33-107">[in]カルチャ識別子。</span><span class="sxs-lookup"><span data-stu-id="c1e33-107">[in] A culture identifier.</span></span> <span data-ttu-id="c1e33-108">-1 を渡す`lcid`の既定のカルチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="c1e33-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="c1e33-109">[in]HRESULT。</span><span class="sxs-lookup"><span data-stu-id="c1e33-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="c1e33-110">[out]正常完了時にエラー メッセージを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="c1e33-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="c1e33-111">[in]エラー メッセージのバッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="c1e33-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="c1e33-112">[in]無視されます。</span><span class="sxs-lookup"><span data-stu-id="c1e33-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="c1e33-113">[out]エラー メッセージの長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c1e33-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1e33-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="c1e33-114">Return Value</span></span>  
 <span data-ttu-id="c1e33-115">このメソッドは、次の値だけでなく、WinError.h で定義されている標準の COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="c1e33-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="c1e33-116">リターン コード</span><span class="sxs-lookup"><span data-stu-id="c1e33-116">Return code</span></span>|<span data-ttu-id="c1e33-117">説明</span><span class="sxs-lookup"><span data-stu-id="c1e33-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c1e33-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="c1e33-118">S_OK</span></span>|<span data-ttu-id="c1e33-119">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="c1e33-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="c1e33-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c1e33-120">E_INVALIDARG</span></span>|<span data-ttu-id="c1e33-121">`szBuffer` null、または`iMax`はゼロ (0)。</span><span class="sxs-lookup"><span data-stu-id="c1e33-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1e33-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="c1e33-122">Remarks</span></span>  
 <span data-ttu-id="c1e33-123">メソッドが正常に完了しない場合`szBuffer`空の文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c1e33-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1e33-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="c1e33-124">Requirements</span></span>  
 <span data-ttu-id="c1e33-125">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1e33-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1e33-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c1e33-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1e33-127">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1e33-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1e33-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1e33-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1e33-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1e33-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c1e33-130">LoadStringRC 関数</span><span class="sxs-lookup"><span data-stu-id="c1e33-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="c1e33-131">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="c1e33-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

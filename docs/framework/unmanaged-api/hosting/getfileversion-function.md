---
title: GetFileVersion 関数
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d25a3ccdd66ff7acb70f1f5e6c60157b53cc97c5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628458"
---
# <a name="getfileversion-function"></a><span data-ttu-id="232b6-102">GetFileVersion 関数</span><span class="sxs-lookup"><span data-stu-id="232b6-102">GetFileVersion Function</span></span>
<span data-ttu-id="232b6-103">指定したバッファーを使用して、指定したファイルの共通言語ランタイム (CLR) バージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="232b6-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="232b6-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="232b6-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="232b6-105">構文</span><span class="sxs-lookup"><span data-stu-id="232b6-105">Syntax</span></span>  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="232b6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="232b6-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="232b6-107">[in]調査するファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="232b6-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="232b6-108">[入力、出力]返されるバージョンについては、割り当てられたバッファー。</span><span class="sxs-lookup"><span data-stu-id="232b6-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="232b6-109">[in]ワイド文字単位のサイズの`szBuffer`します。</span><span class="sxs-lookup"><span data-stu-id="232b6-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="232b6-110">[out]サイズ (バイト単位)、返された`szBuffer`します。</span><span class="sxs-lookup"><span data-stu-id="232b6-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="232b6-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="232b6-111">Requirements</span></span>  
 <span data-ttu-id="232b6-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="232b6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="232b6-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="232b6-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="232b6-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="232b6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="232b6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="232b6-115">See also</span></span>

- [<span data-ttu-id="232b6-116">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="232b6-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

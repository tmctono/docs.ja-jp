---
title: _CorExeMain2 関数
ms.date: 03/30/2017
api_name:
- _CorExeMain2
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain2
helpviewer_keywords:
- _CorExeMain2 function [.NET Framework hosting]
ms.assetid: 72ea68b4-689f-4733-9416-9664b75e8892
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f968d84ae695eb1da127538ebdc5e4f55d6ebf39
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183158"
---
# <a name="corexemain2-function"></a><span data-ttu-id="cf02a-102">_CorExeMain2 関数</span><span class="sxs-lookup"><span data-stu-id="cf02a-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="cf02a-103">指定されたメモリ マップト コードのエントリ ポイントを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf02a-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="cf02a-104">この関数は、オペレーティング システム ローダーによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cf02a-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf02a-105">構文</span><span class="sxs-lookup"><span data-stu-id="cf02a-105">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf02a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf02a-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="cf02a-107">[in]メモリ マップト コードへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cf02a-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="cf02a-108">[in]要素の数`pUnmappedPE`を保持できます。</span><span class="sxs-lookup"><span data-stu-id="cf02a-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="cf02a-109">[in]実行可能イメージの名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cf02a-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="cf02a-110">[in]ローダーのファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="cf02a-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="cf02a-111">[in]コマンド ライン パラメーター、存在する場合。</span><span class="sxs-lookup"><span data-stu-id="cf02a-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf02a-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="cf02a-112">Requirements</span></span>  
 <span data-ttu-id="cf02a-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf02a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf02a-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cf02a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf02a-115">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="cf02a-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="cf02a-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="cf02a-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cf02a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf02a-117">See also</span></span>

- [<span data-ttu-id="cf02a-118">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="cf02a-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)

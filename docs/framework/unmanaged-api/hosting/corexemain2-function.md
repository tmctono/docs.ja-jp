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
ms.openlocfilehash: 8202fe4ec3ae6ef96440f203c5aea6db84744a72
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616582"
---
# <a name="_corexemain2-function"></a><span data-ttu-id="3653e-102">_CorExeMain2 関数</span><span class="sxs-lookup"><span data-stu-id="3653e-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="3653e-103">指定されたメモリ マップト コードのエントリ ポイントを実行します。</span><span class="sxs-lookup"><span data-stu-id="3653e-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="3653e-104">この関数は、オペレーティング システム ローダーによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3653e-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3653e-105">構文</span><span class="sxs-lookup"><span data-stu-id="3653e-105">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3653e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3653e-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="3653e-107">からメモリマップトコードへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3653e-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="3653e-108">から保持できる要素の数 `pUnmappedPE` 。</span><span class="sxs-lookup"><span data-stu-id="3653e-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="3653e-109">から実行可能イメージの名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3653e-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="3653e-110">からローダーファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="3653e-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="3653e-111">からコマンドラインパラメーター (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="3653e-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3653e-112">要件</span><span class="sxs-lookup"><span data-stu-id="3653e-112">Requirements</span></span>  
 <span data-ttu-id="3653e-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3653e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3653e-114">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="3653e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3653e-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3653e-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3653e-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3653e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3653e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3653e-117">See also</span></span>

- [<span data-ttu-id="3653e-118">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="3653e-118">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)

---
title: GetCORVersion 関数
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f66e00c3334aecdf8c653f57e28d1b327c4170e3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094068"
---
# <a name="getcorversion-function"></a><span data-ttu-id="f5d5b-102">GetCORVersion 関数</span><span class="sxs-lookup"><span data-stu-id="f5d5b-102">GetCORVersion Function</span></span>
<span data-ttu-id="f5d5b-103">現在のプロセスで実行されている共通言語ランタイム (CLR) のバージョン番号を返します。</span><span class="sxs-lookup"><span data-stu-id="f5d5b-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="f5d5b-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="f5d5b-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5d5b-105">構文</span><span class="sxs-lookup"><span data-stu-id="f5d5b-105">Syntax</span></span>  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="f5d5b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5d5b-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="f5d5b-107">CLR がプロセスに現在読み込まれてはランタイムのバージョンを指定する文字列を返すバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f5d5b-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="f5d5b-108">渡される文字列として返される文字列は同じ形式を取ります[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)、たとえば、"v1.0.1216"。</span><span class="sxs-lookup"><span data-stu-id="f5d5b-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="f5d5b-109">ランタイムがプロセスにまだ読み込まれていない場合は、コンピューターにインストールされているランタイムの最新バージョンの適切なディレクトリ情報を返します。</span><span class="sxs-lookup"><span data-stu-id="f5d5b-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f5d5b-110">文字数 (`WCHAR`秒) 内に保持することができますを`pbuffer`します。</span><span class="sxs-lookup"><span data-stu-id="f5d5b-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="f5d5b-111">実際に返される文字数へのポインター`pbuffer`します。</span><span class="sxs-lookup"><span data-stu-id="f5d5b-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="f5d5b-112">場合`pbuffer`が null ポインターの場合、ランタイムが E_POINTER を返します。</span><span class="sxs-lookup"><span data-stu-id="f5d5b-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="f5d5b-113">文字の数が大きい場合の長さ、`pbuffer`ランタイムは ERROR_INSUFFICIENT_BUFFER を返します。</span><span class="sxs-lookup"><span data-stu-id="f5d5b-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5d5b-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="f5d5b-114">Requirements</span></span>  
 <span data-ttu-id="f5d5b-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5d5b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5d5b-116">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f5d5b-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5d5b-117">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5d5b-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5d5b-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5d5b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5d5b-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5d5b-119">See also</span></span>

- [<span data-ttu-id="f5d5b-120">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="f5d5b-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

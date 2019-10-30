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
ms.openlocfilehash: 1283abaf6b08af1d842d8fe4469f7f6c15e38ec5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136421"
---
# <a name="getcorversion-function"></a><span data-ttu-id="4f530-102">GetCORVersion 関数</span><span class="sxs-lookup"><span data-stu-id="4f530-102">GetCORVersion Function</span></span>
<span data-ttu-id="4f530-103">現在のプロセスで実行されている共通言語ランタイム (CLR) のバージョン番号を返します。</span><span class="sxs-lookup"><span data-stu-id="4f530-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="4f530-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="4f530-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f530-105">構文</span><span class="sxs-lookup"><span data-stu-id="4f530-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="4f530-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4f530-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="4f530-107">現在プロセスに読み込まれているランタイムのバージョンを指定する文字列を CLR が返すバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4f530-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="4f530-108">返される文字列は、 [Corbindtoruntimeex](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)に渡される文字列と同じ形式になります (例、"v 1.0.1216")。</span><span class="sxs-lookup"><span data-stu-id="4f530-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="4f530-109">ランタイムがまだプロセスに読み込まれていない場合、関数はコンピューターにインストールされている最新バージョンのランタイムの適切なディレクトリ情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4f530-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="4f530-110">`pbuffer`に保持できる文字の数 (`WCHAR`s)。</span><span class="sxs-lookup"><span data-stu-id="4f530-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="4f530-111">`pbuffer`に実際に返された文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4f530-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="4f530-112">`pbuffer` が null ポインターの場合、ランタイムは E_POINTER を返します。</span><span class="sxs-lookup"><span data-stu-id="4f530-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="4f530-113">文字数が `pbuffer` の長さより大きい場合、ランタイムは ERROR_INSUFFICIENT_BUFFER を返します。</span><span class="sxs-lookup"><span data-stu-id="4f530-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f530-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="4f530-114">Requirements</span></span>  
 <span data-ttu-id="4f530-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f530-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f530-116">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4f530-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f530-117">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4f530-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f530-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f530-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f530-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f530-119">See also</span></span>

- [<span data-ttu-id="4f530-120">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="4f530-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

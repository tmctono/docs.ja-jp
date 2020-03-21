---
title: GetCORSystemDirectory 関数
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
ms.openlocfilehash: bdafacfe52d678aacfcd44de1e924bcb88547424
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178202"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="37ab2-102">GetCORSystemDirectory 関数</span><span class="sxs-lookup"><span data-stu-id="37ab2-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="37ab2-103">プロセスに読み込まれる共通言語ランタイム (CLR) のインストール ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="37ab2-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="37ab2-104">インストール ディレクトリは、"c:\windows\microsoft.net\framework\v1.0.3705" など、完全修飾ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="37ab2-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="37ab2-105">この関数の使用は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="37ab2-105">This function is deprecated.</span></span> <span data-ttu-id="37ab2-106">これは、.NET フレームワーク 4 で提供[されるメソッドに](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="37ab2-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37ab2-107">構文</span><span class="sxs-lookup"><span data-stu-id="37ab2-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="37ab2-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="37ab2-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="37ab2-109">[アウト]プロセスに読み込まれるランタイムのインストール ディレクトリの完全修飾名を含む文字列をランタイムが返すバッファー。</span><span class="sxs-lookup"><span data-stu-id="37ab2-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="37ab2-110">ランタイムがまだプロセスに読み込まれていない場合、この関数は、コンピューターにインストールされている最新バージョンのランタイムに対応するディレクトリ情報を返します。</span><span class="sxs-lookup"><span data-stu-id="37ab2-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="37ab2-111">[in]のサイズ (バイト単位)`pbuffer`です。</span><span class="sxs-lookup"><span data-stu-id="37ab2-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="37ab2-112">[アウト]で返される文字数`pbuffer`。</span><span class="sxs-lookup"><span data-stu-id="37ab2-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37ab2-113">解説</span><span class="sxs-lookup"><span data-stu-id="37ab2-113">Remarks</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="37ab2-114">CLR のバージョン 4 を実行しているプロセスでは、この関数を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="37ab2-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="37ab2-115">以前のバージョンの CLR がコンピューターにインストールされている場合、この関数は、そのバージョンのインストール ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="37ab2-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37ab2-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="37ab2-116">Requirements</span></span>  
 <span data-ttu-id="37ab2-117">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37ab2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37ab2-118">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="37ab2-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="37ab2-119">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="37ab2-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37ab2-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37ab2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ab2-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="37ab2-121">See also</span></span>

- [<span data-ttu-id="37ab2-122">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="37ab2-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

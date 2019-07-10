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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: deec4d40270a11b9e48a0ab39504d774314c077c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736190"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="ef3cd-102">GetCORSystemDirectory 関数</span><span class="sxs-lookup"><span data-stu-id="ef3cd-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="ef3cd-103">プロセスに読み込まれる共通言語ランタイム (CLR) のインストール ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="ef3cd-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="ef3cd-104">インストール ディレクトリは、完全修飾"c:\windows\microsoft.net\framework\v1.0.3705"など。</span><span class="sxs-lookup"><span data-stu-id="ef3cd-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="ef3cd-105">この関数が非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="ef3cd-105">This function is deprecated.</span></span> <span data-ttu-id="ef3cd-106">それは置き換えられて、 [iclrruntimeinfo::getruntimedirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) .NET Framework 4 で提供されるメソッド。</span><span class="sxs-lookup"><span data-stu-id="ef3cd-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef3cd-107">構文</span><span class="sxs-lookup"><span data-stu-id="ef3cd-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="ef3cd-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ef3cd-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="ef3cd-109">[out]ランタイムがプロセスに読み込まれたランタイムのインストール ディレクトリの完全修飾名を含む文字列を返すバッファー。</span><span class="sxs-lookup"><span data-stu-id="ef3cd-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="ef3cd-110">ランタイムがプロセスにまだ読み込まれていない場合は、コンピューターにインストールされているランタイムの最新バージョンの適切なディレクトリ情報を返します。</span><span class="sxs-lookup"><span data-stu-id="ef3cd-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="ef3cd-111">[in]サイズ (バイト単位) の`pbuffer`します。</span><span class="sxs-lookup"><span data-stu-id="ef3cd-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="ef3cd-112">[out]返される文字数`pbuffer`します。</span><span class="sxs-lookup"><span data-stu-id="ef3cd-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef3cd-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="ef3cd-113">Remarks</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ef3cd-114">CLR の version 4 を実行しているプロセスでは、この関数は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ef3cd-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="ef3cd-115">CLR の以前のバージョンは、コンピューターにインストールされて、この関数はそのバージョンのインストール ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="ef3cd-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef3cd-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="ef3cd-116">Requirements</span></span>  
 <span data-ttu-id="ef3cd-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef3cd-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef3cd-118">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ef3cd-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef3cd-119">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef3cd-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef3cd-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef3cd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef3cd-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef3cd-121">See also</span></span>

- [<span data-ttu-id="ef3cd-122">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="ef3cd-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

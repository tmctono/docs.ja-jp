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
ms.openlocfilehash: 567e6533a9a9ac718f8b5acac769295c104f7f3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628100"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="368b8-102">GetCORSystemDirectory 関数</span><span class="sxs-lookup"><span data-stu-id="368b8-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="368b8-103">プロセスに読み込まれる共通言語ランタイム (CLR) のインストール ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="368b8-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="368b8-104">インストール ディレクトリは、完全修飾"c:\windows\microsoft.net\framework\v1.0.3705"など。</span><span class="sxs-lookup"><span data-stu-id="368b8-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="368b8-105">この関数が非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="368b8-105">This function is deprecated.</span></span> <span data-ttu-id="368b8-106">それは置き換えられて、 [iclrruntimeinfo::getruntimedirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)メソッドで提供される、 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="368b8-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="368b8-107">構文</span><span class="sxs-lookup"><span data-stu-id="368b8-107">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="368b8-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="368b8-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="368b8-109">[out]ランタイムがプロセスに読み込まれたランタイムのインストール ディレクトリの完全修飾名を含む文字列を返すバッファー。</span><span class="sxs-lookup"><span data-stu-id="368b8-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="368b8-110">ランタイムがプロセスにまだ読み込まれていない場合は、コンピューターにインストールされているランタイムの最新バージョンの適切なディレクトリ情報を返します。</span><span class="sxs-lookup"><span data-stu-id="368b8-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="368b8-111">[in]サイズ (バイト単位) の`pbuffer`します。</span><span class="sxs-lookup"><span data-stu-id="368b8-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="368b8-112">[out]返される文字数`pbuffer`します。</span><span class="sxs-lookup"><span data-stu-id="368b8-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="368b8-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="368b8-113">Remarks</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="368b8-114">CLR の version 4 を実行しているプロセスでは、この関数は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="368b8-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="368b8-115">CLR の以前のバージョンは、コンピューターにインストールされて、この関数はそのバージョンのインストール ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="368b8-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="368b8-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="368b8-116">Requirements</span></span>  
 <span data-ttu-id="368b8-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="368b8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="368b8-118">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="368b8-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="368b8-119">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="368b8-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="368b8-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="368b8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="368b8-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="368b8-121">See also</span></span>

- [<span data-ttu-id="368b8-122">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="368b8-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

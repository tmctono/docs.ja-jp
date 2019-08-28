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
ms.openlocfilehash: d30384ea8b9ff4eee41abd43ae39486f770039e7
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041420"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="6ce4f-102">GetCORSystemDirectory 関数</span><span class="sxs-lookup"><span data-stu-id="6ce4f-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="6ce4f-103">プロセスに読み込まれる共通言語ランタイム (CLR) のインストールディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="6ce4f-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="6ce4f-104">インストールディレクトリは完全に修飾されています。たとえば、"c:\windows\microsoft.net\framework\v1.0.3705" のようになります。</span><span class="sxs-lookup"><span data-stu-id="6ce4f-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="6ce4f-105">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="6ce4f-105">This function is deprecated.</span></span> <span data-ttu-id="6ce4f-106">.NET Framework 4 で提供される[ICLRRuntimeInfo:: GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)メソッドに置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="6ce4f-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ce4f-107">構文</span><span class="sxs-lookup"><span data-stu-id="6ce4f-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="6ce4f-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ce4f-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="6ce4f-109">入出力プロセスに読み込まれたランタイムのインストールディレクトリの完全修飾名が含まれた文字列をランタイムが返すバッファー。</span><span class="sxs-lookup"><span data-stu-id="6ce4f-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="6ce4f-110">ランタイムがまだプロセスに読み込まれていない場合、関数はコンピューターにインストールされている最新バージョンのランタイムの適切なディレクトリ情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6ce4f-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="6ce4f-111">からの`pbuffer`サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="6ce4f-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="6ce4f-112">入出力で`pbuffer`返された文字数。</span><span class="sxs-lookup"><span data-stu-id="6ce4f-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ce4f-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="6ce4f-113">Remarks</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="6ce4f-114">CLR のバージョン4を実行しているプロセスでは、この関数を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6ce4f-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="6ce4f-115">コンピューターに以前のバージョンの CLR がインストールされている場合、この関数はそのバージョンのインストールディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="6ce4f-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ce4f-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="6ce4f-116">Requirements</span></span>  
 <span data-ttu-id="6ce4f-117">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ce4f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ce4f-118">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6ce4f-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ce4f-119">**ライブラリ**Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6ce4f-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ce4f-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ce4f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ce4f-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ce4f-121">See also</span></span>

- [<span data-ttu-id="6ce4f-122">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="6ce4f-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

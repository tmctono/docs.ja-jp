---
title: IAssemblyCache::InstallAssembly メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyCache.InstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::InstallAssembly
helpviewer_keywords:
- InstallAssembly method [.NET Framework fusion]
- IAssemblyCache::InstallAssembly method [.NET Framework fusion]
ms.assetid: 33c1d269-c85e-4cb1-b0e6-1c510c8fb5fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50152b72cade763a5b890c0c9d45109d88ce65a7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469210"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="cbe90-102">IAssemblyCache::InstallAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="cbe90-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="cbe90-103">指定したアセンブリをグローバル アセンブリ キャッシュにインストールします。</span><span class="sxs-lookup"><span data-stu-id="cbe90-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbe90-104">構文</span><span class="sxs-lookup"><span data-stu-id="cbe90-104">Syntax</span></span>  
  
```  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbe90-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cbe90-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="cbe90-106">[in]ものがありますで定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="cbe90-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="cbe90-107">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cbe90-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="cbe90-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="cbe90-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="cbe90-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="cbe90-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="cbe90-110">[in]インストールするアセンブリのマニフェストへのパス。</span><span class="sxs-lookup"><span data-stu-id="cbe90-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="cbe90-111">[in]A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)インストール用のデータを含む構造体。</span><span class="sxs-lookup"><span data-stu-id="cbe90-111">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbe90-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="cbe90-112">Requirements</span></span>  
 <span data-ttu-id="cbe90-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbe90-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbe90-114">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="cbe90-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cbe90-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbe90-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe90-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbe90-116">See also</span></span>
- [<span data-ttu-id="cbe90-117">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cbe90-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)

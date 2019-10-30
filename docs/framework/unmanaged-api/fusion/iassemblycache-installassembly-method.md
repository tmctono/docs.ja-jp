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
ms.openlocfilehash: ec08c786992996ec6f44038ff3c1596cada88484
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127083"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="2a23a-102">IAssemblyCache::InstallAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="2a23a-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="2a23a-103">指定したアセンブリをグローバルアセンブリキャッシュにインストールします。</span><span class="sxs-lookup"><span data-stu-id="2a23a-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a23a-104">構文</span><span class="sxs-lookup"><span data-stu-id="2a23a-104">Syntax</span></span>  
  
```cpp  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a23a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a23a-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="2a23a-106">からFusion に定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="2a23a-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="2a23a-107">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2a23a-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="2a23a-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="2a23a-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="2a23a-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="2a23a-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="2a23a-110">からインストールするアセンブリのマニフェストへのパス。</span><span class="sxs-lookup"><span data-stu-id="2a23a-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="2a23a-111">からインストール用のデータを格納する[FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="2a23a-111">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a23a-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="2a23a-112">Requirements</span></span>  
 <span data-ttu-id="2a23a-113">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a23a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a23a-114">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2a23a-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2a23a-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a23a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a23a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a23a-116">See also</span></span>

- [<span data-ttu-id="2a23a-117">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a23a-117">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)

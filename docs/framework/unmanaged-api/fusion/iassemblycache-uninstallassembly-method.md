---
title: IAssemblyCache::UninstallAssembly メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyCache.UninstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::UninstallAssembly
helpviewer_keywords:
- UninstallAssembly method [.NET Framework fusion]
- IAssemblyCache::UninstallAssembly method [.NET Framework fusion]
ms.assetid: 973b2c44-8dfc-40c1-9035-10f4846627e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75ef24162adbb653671ed070587e7155fae6b949
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697746"
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="99be1-102">IAssemblyCache::UninstallAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="99be1-102">IAssemblyCache::UninstallAssembly Method</span></span>
<span data-ttu-id="99be1-103">指定したアセンブリをグローバル アセンブリ キャッシュからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="99be1-103">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99be1-104">構文</span><span class="sxs-lookup"><span data-stu-id="99be1-104">Syntax</span></span>  
  
```  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99be1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="99be1-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="99be1-106">[in]ものがありますで定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="99be1-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="99be1-107">[in]アンインストールするアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="99be1-107">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="99be1-108">[in]A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)アセンブリのインストール データを含む構造体。</span><span class="sxs-lookup"><span data-stu-id="99be1-108">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="99be1-109">[out] 省略可能ものがありますで定義されている配置の値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="99be1-109">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="99be1-110">使用できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="99be1-110">Possible values include the following:</span></span>  
  
- <span data-ttu-id="99be1-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span><span class="sxs-lookup"><span data-stu-id="99be1-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
- <span data-ttu-id="99be1-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span><span class="sxs-lookup"><span data-stu-id="99be1-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
- <span data-ttu-id="99be1-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span><span class="sxs-lookup"><span data-stu-id="99be1-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
- <span data-ttu-id="99be1-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span><span class="sxs-lookup"><span data-stu-id="99be1-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
- <span data-ttu-id="99be1-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span><span class="sxs-lookup"><span data-stu-id="99be1-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
- <span data-ttu-id="99be1-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span><span class="sxs-lookup"><span data-stu-id="99be1-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99be1-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="99be1-117">Requirements</span></span>  
 <span data-ttu-id="99be1-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99be1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99be1-119">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="99be1-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="99be1-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99be1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99be1-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="99be1-121">See also</span></span>

- [<span data-ttu-id="99be1-122">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="99be1-122">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)

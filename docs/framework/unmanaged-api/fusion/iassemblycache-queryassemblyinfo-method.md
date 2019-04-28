---
title: IAssemblyCache::QueryAssemblyInfo メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyCache.QueryAssemblyInfo
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::QueryAssemblyInfo
helpviewer_keywords:
- IAssemblyCache::QueryAssemblyInfo method [.NET Framework fusion]
- QueryAssemblyInfo method [.NET Framework fusion]
ms.assetid: 09313cb5-06f6-43bd-94f4-1055c6b0c99a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81b647032b2e9474e3b4472552ed884cec92ffc3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697525"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="b5664-102">IAssemblyCache::QueryAssemblyInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="b5664-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="b5664-103">指定したアセンブリについて、要求されたデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="b5664-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5664-104">構文</span><span class="sxs-lookup"><span data-stu-id="b5664-104">Syntax</span></span>  
  
```  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5664-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b5664-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="b5664-106">[in]ものがありますで定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="b5664-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="b5664-107">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b5664-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="b5664-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="b5664-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
- <span data-ttu-id="b5664-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="b5664-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="b5664-110">[in]データの取得対象のアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="b5664-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="b5664-111">[入力、出力][ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md)アセンブリについてのデータを含む構造体。</span><span class="sxs-lookup"><span data-stu-id="b5664-111">[in, out] An [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5664-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="b5664-112">Requirements</span></span>  
 <span data-ttu-id="b5664-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5664-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5664-114">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b5664-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b5664-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5664-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5664-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5664-116">See also</span></span>

- [<span data-ttu-id="b5664-117">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b5664-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)

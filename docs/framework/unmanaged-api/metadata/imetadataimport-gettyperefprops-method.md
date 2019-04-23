---
title: IMetaDataImport::GetTypeRefProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 808c48bb0c516c51f39a8424acf49869b1bc9208
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165231"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="c1549-102">IMetaDataImport::GetTypeRefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="c1549-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="c1549-103">関連付けられているメタデータを取得、<xref:System.Type>指定した TypeRef トークンによって参照されています。</span><span class="sxs-lookup"><span data-stu-id="c1549-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1549-104">構文</span><span class="sxs-lookup"><span data-stu-id="c1549-104">Syntax</span></span>  
  
```  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1549-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c1549-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="c1549-106">[in]メタデータを返す型を表す TypeRef トークンです。</span><span class="sxs-lookup"><span data-stu-id="c1549-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="c1549-107">[out]これで、参照が行われるスコープへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c1549-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="c1549-108">この値は、AssemblyRef または ModuleRef トークンです。</span><span class="sxs-lookup"><span data-stu-id="c1549-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="c1549-109">[out]型名を含むバッファー。</span><span class="sxs-lookup"><span data-stu-id="c1549-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c1549-110">[in]要求されたサイズのワイド文字単位`szName`します。</span><span class="sxs-lookup"><span data-stu-id="c1549-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="c1549-111">[out]ワイド文字で返されるサイズ`szName`します。</span><span class="sxs-lookup"><span data-stu-id="c1549-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1549-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="c1549-112">Requirements</span></span>  
 <span data-ttu-id="c1549-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1549-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1549-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c1549-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1549-115">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c1549-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c1549-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1549-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1549-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1549-117">See also</span></span>

- [<span data-ttu-id="c1549-118">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1549-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c1549-119">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1549-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

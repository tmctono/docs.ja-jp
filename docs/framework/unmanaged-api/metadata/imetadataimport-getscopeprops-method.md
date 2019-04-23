---
title: IMetaDataImport::GetScopeProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 17568a46c8e946989af0e401366d7eaa885886da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220969"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="27fe3-102">IMetaDataImport::GetScopeProps メソッド</span><span class="sxs-lookup"><span data-stu-id="27fe3-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="27fe3-103">現在のメタデータ スコープにあるアセンブリまたはモジュールの名前、およびオプションでバージョン ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="27fe3-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27fe3-104">構文</span><span class="sxs-lookup"><span data-stu-id="27fe3-104">Syntax</span></span>  
  
```  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27fe3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="27fe3-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="27fe3-106">[out]アセンブリまたはモジュール名のバッファー。</span><span class="sxs-lookup"><span data-stu-id="27fe3-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="27fe3-107">[in]ワイド文字単位サイズ`szName`します。</span><span class="sxs-lookup"><span data-stu-id="27fe3-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="27fe3-108">[out]返されるワイド文字数`szName`します。</span><span class="sxs-lookup"><span data-stu-id="27fe3-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="27fe3-109">[out] 省略可能アセンブリまたはモジュールのバージョンを一意に識別する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="27fe3-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27fe3-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="27fe3-110">Remarks</span></span>  
 <span data-ttu-id="27fe3-111">[Imetadataemit::setmoduleprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)メソッドを使用して、これらのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="27fe3-111">The [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27fe3-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="27fe3-112">Requirements</span></span>  
 <span data-ttu-id="27fe3-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="27fe3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27fe3-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="27fe3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27fe3-115">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="27fe3-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27fe3-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27fe3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27fe3-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="27fe3-117">See also</span></span>

- [<span data-ttu-id="27fe3-118">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27fe3-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="27fe3-119">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27fe3-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

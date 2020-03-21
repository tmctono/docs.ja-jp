---
title: IMetaDataImport::GetModuleRefProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type:
- apiref
ms.openlocfilehash: f46033b9e643ef6b4a0063c4995b8c024b8c1f7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175357"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="63a39-102">IMetaDataImport::GetModuleRefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="63a39-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="63a39-103">指定したメタデータ トークンによって参照されるモジュールの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="63a39-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63a39-104">構文</span><span class="sxs-lookup"><span data-stu-id="63a39-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,
   [in]  ULONG               cchName,
   [out] ULONG               *pchName
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63a39-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="63a39-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="63a39-106">[in]メタデータ情報を取得するモジュールを参照する ModuleRef メタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="63a39-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="63a39-107">[アウト]モジュール名を保持するバッファー。</span><span class="sxs-lookup"><span data-stu-id="63a39-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="63a39-108">[in]ワイド文字で指定`szName`されたサイズ。</span><span class="sxs-lookup"><span data-stu-id="63a39-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="63a39-109">[アウト]ワイド文字`szName`で返されるサイズ。</span><span class="sxs-lookup"><span data-stu-id="63a39-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63a39-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="63a39-110">Requirements</span></span>  
 <span data-ttu-id="63a39-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63a39-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63a39-112">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="63a39-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="63a39-113">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="63a39-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="63a39-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63a39-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63a39-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="63a39-115">See also</span></span>

- [<span data-ttu-id="63a39-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="63a39-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="63a39-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="63a39-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

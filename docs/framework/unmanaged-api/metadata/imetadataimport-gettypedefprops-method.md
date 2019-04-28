---
title: IMetaDataImport::GetTypeDefProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a482c7a06efe888408206f2de569e0a8739b85b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777508"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="1ff34-102">IMetaDataImport::GetTypeDefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="1ff34-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="1ff34-103">メタデータ情報を返します、<xref:System.Type>指定した TypeDef トークンによって表されます。</span><span class="sxs-lookup"><span data-stu-id="1ff34-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ff34-104">構文</span><span class="sxs-lookup"><span data-stu-id="1ff34-104">Syntax</span></span>  
  
```  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ff34-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1ff34-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="1ff34-106">[in]メタデータを返す型を表す TypeDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="1ff34-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="1ff34-107">[out]型名を含むバッファー。</span><span class="sxs-lookup"><span data-stu-id="1ff34-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="1ff34-108">[in]ワイド文字単位サイズ`szTypeDef`します。</span><span class="sxs-lookup"><span data-stu-id="1ff34-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="1ff34-109">[out]返されるワイド文字数`szTypeDef`します。</span><span class="sxs-lookup"><span data-stu-id="1ff34-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="1ff34-110">[out]型定義を変更する任意のフラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1ff34-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="1ff34-111">この値はビットマスクから、 [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="1ff34-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="1ff34-112">[out]要求された型の基本型を表す TypeDef または TypeRef メタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="1ff34-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ff34-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="1ff34-113">Requirements</span></span>  
 <span data-ttu-id="1ff34-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ff34-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ff34-115">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1ff34-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1ff34-116">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="1ff34-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1ff34-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ff34-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ff34-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ff34-118">See also</span></span>

- [<span data-ttu-id="1ff34-119">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1ff34-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1ff34-120">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1ff34-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

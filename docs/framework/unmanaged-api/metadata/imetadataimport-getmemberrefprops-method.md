---
title: IMetaDataImport::GetMemberRefProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
ms.openlocfilehash: a61254ba751e47b0089a3f7528aca337a32e2db3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175370"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="5b1dc-102">IMetaDataImport::GetMemberRefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="5b1dc-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="5b1dc-103">指定したトークンによって参照されるメンバーに関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b1dc-104">構文</span><span class="sxs-lookup"><span data-stu-id="5b1dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,
   [out] mdToken           *ptk,
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b1dc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5b1dc-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="5b1dc-106">[in]関連するメタデータを返す MemberRef トークン。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="5b1dc-107">[アウト]メンバーを宣言するクラスを表す TypeDef または TypeRef トークン、またはメンバーを宣言するモジュール クラスを表す ModuleRef トークン、またはメンバーを表す MethodDef。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="5b1dc-108">[アウト]メンバーの名前の文字列バッファー。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="5b1dc-109">[in]要求されたサイズは、 の`szMember`ワイド文字で表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="5b1dc-110">[アウト]返されるサイズは、 の`szMember`ワイド文字で表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="5b1dc-111">[アウト]メンバーのバイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="5b1dc-112">[アウト]のサイズ (バイト`ppvSigBlob`単位)</span><span class="sxs-lookup"><span data-stu-id="5b1dc-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b1dc-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="5b1dc-113">Requirements</span></span>  
 <span data-ttu-id="5b1dc-114">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b1dc-115">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="5b1dc-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b1dc-116">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="5b1dc-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b1dc-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b1dc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b1dc-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b1dc-118">See also</span></span>

- [<span data-ttu-id="5b1dc-119">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b1dc-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5b1dc-120">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b1dc-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

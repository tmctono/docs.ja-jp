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
ms.openlocfilehash: 1d6d66ea62cbf679f722f830b3638455001aedd6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437493"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="b1a14-102">IMetaDataImport::GetMemberRefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="b1a14-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="b1a14-103">指定したトークンによって参照されるメンバーに関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="b1a14-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1a14-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1a14-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b1a14-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1a14-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="b1a14-106">から関連付けられたメタデータを返す MemberRef トークン。</span><span class="sxs-lookup"><span data-stu-id="b1a14-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="b1a14-107">入出力メンバーを宣言するクラスを表す TypeDef または TypeRef または TypeSpec トークン、またはメンバーを宣言するモジュールクラスを表す ModuleRef トークン、またはメンバーを表す MethodDef。</span><span class="sxs-lookup"><span data-stu-id="b1a14-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="b1a14-108">入出力メンバーの名前の文字列バッファー。</span><span class="sxs-lookup"><span data-stu-id="b1a14-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="b1a14-109">から`szMember`のワイド文字で要求されたサイズ。</span><span class="sxs-lookup"><span data-stu-id="b1a14-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="b1a14-110">入出力`szMember`のワイド文字で返されたサイズ。</span><span class="sxs-lookup"><span data-stu-id="b1a14-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="b1a14-111">入出力メンバーのバイナリメタデータシグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b1a14-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="b1a14-112">入出力`ppvSigBlob`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="b1a14-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1a14-113">要件</span><span class="sxs-lookup"><span data-stu-id="b1a14-113">Requirements</span></span>  
 <span data-ttu-id="b1a14-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1a14-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1a14-115">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="b1a14-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b1a14-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b1a14-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b1a14-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1a14-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1a14-118">参照</span><span class="sxs-lookup"><span data-stu-id="b1a14-118">See also</span></span>

- [<span data-ttu-id="b1a14-119">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1a14-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b1a14-120">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1a14-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

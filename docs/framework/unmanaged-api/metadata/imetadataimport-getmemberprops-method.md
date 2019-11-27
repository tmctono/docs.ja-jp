---
title: IMetaDataImport::GetMemberProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
ms.openlocfilehash: bc5bbba2fa4a95955e52a2e083a2097178b5d96a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437521"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="ba29c-102">IMetaDataImport::GetMemberProps メソッド</span><span class="sxs-lookup"><span data-stu-id="ba29c-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="ba29c-103">指定されたメタデータトークンによって参照される <xref:System.Type> メンバーの、名前、バイナリ署名、相対仮想アドレスなど、指定されたメンバー定義のメタデータに格納されている情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="ba29c-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="ba29c-104">これは単純なヘルパーメソッドです。 *mb*が MethodDef の場合は、 **getmethodprops**が呼び出されます。*mb*が FieldDef の場合は、 **getfieldprops**が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ba29c-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="ba29c-105">詳細については、これらの他の方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba29c-105">See these other methods for details.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="ba29c-106">構文</span><span class="sxs-lookup"><span data-stu-id="ba29c-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] ULONG             *pulCodeRVA,   
   [out] DWORD             *pdwImplFlags,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba29c-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ba29c-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="ba29c-108">から関連付けられているメタデータを取得するメンバーを参照するトークン。</span><span class="sxs-lookup"><span data-stu-id="ba29c-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="ba29c-109">入出力メンバーのクラスを表すメタデータトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ba29c-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="ba29c-110">入出力メンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="ba29c-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="ba29c-111">から`szMember` バッファーのワイド文字単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="ba29c-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="ba29c-112">入出力返される名前のワイド文字単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="ba29c-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="ba29c-113">入出力メンバーに適用されるフラグ値。</span><span class="sxs-lookup"><span data-stu-id="ba29c-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="ba29c-114">入出力メンバーのバイナリメタデータシグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ba29c-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="ba29c-115">入出力`ppvSigBlob`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="ba29c-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="ba29c-116">入出力メンバーの相対仮想アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ba29c-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="ba29c-117">入出力メンバーに関連付けられているメソッド実装フラグ。</span><span class="sxs-lookup"><span data-stu-id="ba29c-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="ba29c-118">入出力<xref:System.ValueType>をマークするフラグ。</span><span class="sxs-lookup"><span data-stu-id="ba29c-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="ba29c-119">これは `ELEMENT_TYPE_*` の値の1つです。</span><span class="sxs-lookup"><span data-stu-id="ba29c-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="ba29c-120">入出力このメンバーによって返される定数文字列値。</span><span class="sxs-lookup"><span data-stu-id="ba29c-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="ba29c-121">入出力`ppValue`の文字単位のサイズ。 `ppValue` が文字列を保持していない場合は0。</span><span class="sxs-lookup"><span data-stu-id="ba29c-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba29c-122">要件</span><span class="sxs-lookup"><span data-stu-id="ba29c-122">Requirements</span></span>  
 <span data-ttu-id="ba29c-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba29c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba29c-124">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="ba29c-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba29c-125">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ba29c-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba29c-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba29c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba29c-127">参照</span><span class="sxs-lookup"><span data-stu-id="ba29c-127">See also</span></span>

- [<span data-ttu-id="ba29c-128">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ba29c-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ba29c-129">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ba29c-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

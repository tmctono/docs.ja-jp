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
ms.openlocfilehash: 6346b1e34e508e5c173bfd0119ac7451d7eef40e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490797"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="dba3b-102">IMetaDataImport::GetTypeDefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="dba3b-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="dba3b-103"><xref:System.Type>指定した TypeDef トークンによって表されるのメタデータ情報を返します。</span><span class="sxs-lookup"><span data-stu-id="dba3b-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dba3b-104">構文</span><span class="sxs-lookup"><span data-stu-id="dba3b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dba3b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dba3b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="dba3b-106">からメタデータを返す型を表す TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="dba3b-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="dba3b-107">入出力型名を格納しているバッファー。</span><span class="sxs-lookup"><span data-stu-id="dba3b-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="dba3b-108">からのワイド文字のサイズ `szTypeDef` 。</span><span class="sxs-lookup"><span data-stu-id="dba3b-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="dba3b-109">入出力で返されたワイド文字の数 `szTypeDef` 。</span><span class="sxs-lookup"><span data-stu-id="dba3b-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="dba3b-110">入出力型定義を変更するすべてのフラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="dba3b-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="dba3b-111">この値は、 [Cortypeattr](cortypeattr-enumeration.md)列挙子のビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="dba3b-111">This value is a bitmask from the [CorTypeAttr](cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="dba3b-112">入出力要求された型の基本型を表す TypeDef または TypeRef メタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="dba3b-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dba3b-113">要件</span><span class="sxs-lookup"><span data-stu-id="dba3b-113">Requirements</span></span>  
 <span data-ttu-id="dba3b-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dba3b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dba3b-115">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="dba3b-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dba3b-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="dba3b-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dba3b-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dba3b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dba3b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="dba3b-118">See also</span></span>

- [<span data-ttu-id="dba3b-119">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dba3b-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="dba3b-120">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dba3b-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

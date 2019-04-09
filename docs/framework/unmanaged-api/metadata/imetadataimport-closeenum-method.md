---
title: IMetaDataImport::CloseEnum メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7846eeceeb4d59c4e9aae73c79172c89184396e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123870"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="de8f9-102">IMetaDataImport::CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="de8f9-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="de8f9-103">指定したハンドルによって識別される列挙子を閉じます。</span><span class="sxs-lookup"><span data-stu-id="de8f9-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de8f9-104">構文</span><span class="sxs-lookup"><span data-stu-id="de8f9-104">Syntax</span></span>  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de8f9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de8f9-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="de8f9-106">[in]閉じる、列挙子のハンドル。</span><span class="sxs-lookup"><span data-stu-id="de8f9-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de8f9-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="de8f9-107">Remarks</span></span>  
 <span data-ttu-id="de8f9-108">指定されたハンドル`hEnum`以前から取得されます`Enum`*名前*呼び出し (たとえば、 [imetadataimport::enumtypedefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md))。</span><span class="sxs-lookup"><span data-stu-id="de8f9-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de8f9-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="de8f9-109">Requirements</span></span>  
 <span data-ttu-id="de8f9-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de8f9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de8f9-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="de8f9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de8f9-112">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="de8f9-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="de8f9-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="de8f9-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="de8f9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="de8f9-114">See also</span></span>

- [<span data-ttu-id="de8f9-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de8f9-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="de8f9-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de8f9-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

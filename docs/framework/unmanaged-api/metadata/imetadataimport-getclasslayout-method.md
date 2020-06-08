---
title: IMetaDataImport::GetClassLayout メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
ms.openlocfilehash: 36c0ffef2d984604be4ae19899e8f3f912cee123
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491473"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="f7b21-102">IMetaDataImport::GetClassLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="f7b21-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="f7b21-103">指定した TypeDef トークンによって参照されるクラスのレイアウト情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="f7b21-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7b21-104">構文</span><span class="sxs-lookup"><span data-stu-id="f7b21-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout  (
   [in]  mdTypeDef          td,
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7b21-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7b21-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f7b21-106">から返されるレイアウトを持つクラスの TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="f7b21-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="f7b21-107">入出力クラスのパックサイズを表す1、2、4、8、または16のいずれかの値。</span><span class="sxs-lookup"><span data-stu-id="f7b21-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="f7b21-108">入出力[COR_FIELD_OFFSET](cor-field-offset-structure.md)値の配列。</span><span class="sxs-lookup"><span data-stu-id="f7b21-108">[out] An array of [COR_FIELD_OFFSET](cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f7b21-109">[in] `rFieldOffset` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="f7b21-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="f7b21-110">入出力で返される要素の数 `rFieldOffset` 。</span><span class="sxs-lookup"><span data-stu-id="f7b21-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="f7b21-111">入出力によって表されるクラスのサイズ (バイト単位) `td` 。</span><span class="sxs-lookup"><span data-stu-id="f7b21-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7b21-112">要件</span><span class="sxs-lookup"><span data-stu-id="f7b21-112">Requirements</span></span>  
 <span data-ttu-id="f7b21-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7b21-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7b21-114">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="f7b21-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f7b21-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f7b21-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f7b21-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7b21-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b21-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7b21-117">See also</span></span>

- [<span data-ttu-id="f7b21-118">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7b21-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f7b21-119">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7b21-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

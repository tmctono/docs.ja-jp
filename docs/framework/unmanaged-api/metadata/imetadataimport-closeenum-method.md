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
ms.openlocfilehash: 5de62db4180a6a9160193053fe42e39cebc34d0e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492494"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="90e84-102">IMetaDataImport::CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="90e84-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="90e84-103">指定したハンドルによって識別される列挙子を閉じます。</span><span class="sxs-lookup"><span data-stu-id="90e84-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90e84-104">構文</span><span class="sxs-lookup"><span data-stu-id="90e84-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90e84-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="90e84-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="90e84-106">から閉じる列挙子のハンドル。</span><span class="sxs-lookup"><span data-stu-id="90e84-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90e84-107">解説</span><span class="sxs-lookup"><span data-stu-id="90e84-107">Remarks</span></span>  
 <span data-ttu-id="90e84-108">によって指定されたハンドル `hEnum` は、前 `Enum` の*名前*の呼び出し (たとえば、 [IMetaDataImport:: enumtypedefs](imetadataimport-enumtypedefs-method.md)) から取得されます。</span><span class="sxs-lookup"><span data-stu-id="90e84-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90e84-109">要件</span><span class="sxs-lookup"><span data-stu-id="90e84-109">Requirements</span></span>  
 <span data-ttu-id="90e84-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90e84-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90e84-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="90e84-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90e84-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="90e84-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90e84-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90e84-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e84-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="90e84-114">See also</span></span>

- [<span data-ttu-id="90e84-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="90e84-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="90e84-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="90e84-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)

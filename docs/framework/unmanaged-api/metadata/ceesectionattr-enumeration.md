---
title: CeeSectionAttr 列挙型
ms.date: 03/30/2017
api_name:
- CeeSectionAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionAttr
helpviewer_keywords:
- CeeSectionAttr enumeration [.NET Framework metadata]
ms.assetid: 0db51881-b869-4677-a715-1726a9216489
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c317524cefd7ed654e76bdd7051cdcd7653062db
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101791"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="55206-102">CeeSectionAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="55206-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="55206-103">使用するセクションの属性を指定する値を提供、 [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="55206-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55206-104">構文</span><span class="sxs-lookup"><span data-stu-id="55206-104">Syntax</span></span>  
  
```  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="55206-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="55206-105">Members</span></span>  
  
|<span data-ttu-id="55206-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="55206-106">Member</span></span>|<span data-ttu-id="55206-107">説明</span><span class="sxs-lookup"><span data-stu-id="55206-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="55206-108">セクションには、属性がありません。</span><span class="sxs-lookup"><span data-stu-id="55206-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="55206-109">セクションには、読み取りのみ可能で、更新されない初期化されたデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="55206-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="55206-110">セクションには、読み取りまたは更新ができる初期化されたデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="55206-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="55206-111">セクションには、読み取りし、実行が許可されている実行可能コードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="55206-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="55206-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="55206-112">Requirements</span></span>  
 <span data-ttu-id="55206-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55206-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55206-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="55206-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="55206-115">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="55206-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="55206-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="55206-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="55206-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="55206-117">See also</span></span>

- [<span data-ttu-id="55206-118">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="55206-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

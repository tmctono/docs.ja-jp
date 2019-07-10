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
ms.openlocfilehash: 61fc71c2ab0a9107f5e9fbb354fe0f8c2fb0dace
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776343"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="ab518-102">CeeSectionAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="ab518-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="ab518-103">使用するセクションの属性を指定する値を提供、 [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ab518-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab518-104">構文</span><span class="sxs-lookup"><span data-stu-id="ab518-104">Syntax</span></span>  
  
```cpp  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="ab518-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ab518-105">Members</span></span>  
  
|<span data-ttu-id="ab518-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ab518-106">Member</span></span>|<span data-ttu-id="ab518-107">説明</span><span class="sxs-lookup"><span data-stu-id="ab518-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="ab518-108">セクションには、属性がありません。</span><span class="sxs-lookup"><span data-stu-id="ab518-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="ab518-109">セクションには、読み取りのみ可能で、更新されない初期化されたデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab518-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="ab518-110">セクションには、読み取りまたは更新ができる初期化されたデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab518-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="ab518-111">セクションには、読み取りし、実行が許可されている実行可能コードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab518-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab518-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="ab518-112">Requirements</span></span>  
 <span data-ttu-id="ab518-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab518-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab518-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ab518-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab518-115">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="ab518-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ab518-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab518-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab518-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab518-117">See also</span></span>

- [<span data-ttu-id="ab518-118">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="ab518-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

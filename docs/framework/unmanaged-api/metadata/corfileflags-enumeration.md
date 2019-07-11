---
title: CorFileFlags 列挙型
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5c6ac7dabd2dfcc7829fd42389c0a6c261fe456d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781869"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="a6997-102">CorFileFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="a6997-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="a6997-103">呼び出しで定義されているファイルの種類を記述する値を含む[imetadataassemblyemit::definefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6997-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6997-104">構文</span><span class="sxs-lookup"><span data-stu-id="a6997-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="a6997-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="a6997-105">Members</span></span>  
  
|<span data-ttu-id="a6997-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a6997-106">Member</span></span>|<span data-ttu-id="a6997-107">説明</span><span class="sxs-lookup"><span data-stu-id="a6997-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="a6997-108">ファイルがリソース ファイルではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="a6997-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="a6997-109">場合によっては、リソース ファイル、ファイルにメタデータが含まれていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="a6997-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6997-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="a6997-110">Requirements</span></span>  
 <span data-ttu-id="a6997-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6997-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6997-112">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="a6997-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="a6997-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6997-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6997-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6997-114">See also</span></span>

- [<span data-ttu-id="a6997-115">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="a6997-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

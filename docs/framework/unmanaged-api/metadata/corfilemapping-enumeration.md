---
title: CorFileMapping 列挙体
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3056836d289383161f9fa538c3c6349f88b6ba6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175618"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="72b85-102">CorFileMapping 列挙体</span><span class="sxs-lookup"><span data-stu-id="72b85-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="72b85-103">呼び出しから返されるファイル マッピングの種類を記述する値が含まれています、 [imetadatainfo::getfilemapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="72b85-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72b85-104">構文</span><span class="sxs-lookup"><span data-stu-id="72b85-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="72b85-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="72b85-105">Members</span></span>  
  
|<span data-ttu-id="72b85-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="72b85-106">Member</span></span>|<span data-ttu-id="72b85-107">説明</span><span class="sxs-lookup"><span data-stu-id="72b85-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="72b85-108">ファイルは、データ ファイルとしてマップされます。</span><span class="sxs-lookup"><span data-stu-id="72b85-108">The file is mapped as a data file.</span></span> <span data-ttu-id="72b85-109">つまり、`SEC_IMAGE`フラグは、Microsoft Win32 に渡されなかった`CreateFileMapping`関数。</span><span class="sxs-lookup"><span data-stu-id="72b85-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="72b85-110">いずれかを使用して、実行するため、ファイルがマップされている、`LoadLibrary`関数または`CreateFileMapping`関数と、`SEC_IMAGE`フラグ。</span><span class="sxs-lookup"><span data-stu-id="72b85-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="72b85-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="72b85-111">Requirements</span></span>  
 <span data-ttu-id="72b85-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72b85-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72b85-113">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="72b85-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="72b85-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72b85-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72b85-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="72b85-115">See also</span></span>

- [<span data-ttu-id="72b85-116">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="72b85-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="72b85-117">GetFileMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="72b85-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)

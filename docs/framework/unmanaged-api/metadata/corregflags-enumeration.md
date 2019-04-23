---
title: CorRegFlags 列挙型
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb6b303fa7569712c854e8dc4e7513d8608e2519
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104963"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="725f7-102">CorRegFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="725f7-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="725f7-103">モジュールまたは複合イメージをインストールするときに登録のために使用するフラグ値を提供します。</span><span class="sxs-lookup"><span data-stu-id="725f7-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="725f7-104">構文</span><span class="sxs-lookup"><span data-stu-id="725f7-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="725f7-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="725f7-105">Members</span></span>  
  
|<span data-ttu-id="725f7-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="725f7-106">Member</span></span>|<span data-ttu-id="725f7-107">説明</span><span class="sxs-lookup"><span data-stu-id="725f7-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="725f7-108">変換先にファイルをコピーしないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="725f7-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="725f7-109">モジュールまたは複合イメージは、構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="725f7-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="725f7-110">モジュールまたは複合にクラスの参照があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="725f7-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="725f7-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="725f7-111">Requirements</span></span>  
 <span data-ttu-id="725f7-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="725f7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="725f7-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="725f7-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="725f7-114">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="725f7-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="725f7-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="725f7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="725f7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="725f7-116">See also</span></span>

- [<span data-ttu-id="725f7-117">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="725f7-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

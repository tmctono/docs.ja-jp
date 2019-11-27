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
ms.openlocfilehash: 79a9e4513a98a29edc11cc76c599f03c9c3a72b4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450112"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="988b9-102">CorRegFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="988b9-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="988b9-103">モジュールまたは複合イメージをインストールするときに登録に使用されるフラグ値を提供します。</span><span class="sxs-lookup"><span data-stu-id="988b9-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="988b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="988b9-104">Syntax</span></span>  
  
```cpp  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="988b9-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="988b9-105">Members</span></span>  
  
|<span data-ttu-id="988b9-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="988b9-106">Member</span></span>|<span data-ttu-id="988b9-107">説明</span><span class="sxs-lookup"><span data-stu-id="988b9-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="988b9-108">転送先にファイルをコピーしないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="988b9-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="988b9-109">モジュールまたは複合が構成であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="988b9-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="988b9-110">モジュールまたは複合にクラス参照があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="988b9-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="988b9-111">要件</span><span class="sxs-lookup"><span data-stu-id="988b9-111">Requirements</span></span>  
 <span data-ttu-id="988b9-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="988b9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="988b9-113">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="988b9-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="988b9-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="988b9-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="988b9-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="988b9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="988b9-116">参照</span><span class="sxs-lookup"><span data-stu-id="988b9-116">See also</span></span>

- [<span data-ttu-id="988b9-117">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="988b9-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

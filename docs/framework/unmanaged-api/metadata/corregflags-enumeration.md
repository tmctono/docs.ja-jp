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
ms.openlocfilehash: cf2a1bca6115902d96f72c19dc469d0a1c8588cd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756218"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="94795-102">CorRegFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="94795-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="94795-103">モジュールまたは複合イメージをインストールするときに登録のために使用するフラグ値を提供します。</span><span class="sxs-lookup"><span data-stu-id="94795-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94795-104">構文</span><span class="sxs-lookup"><span data-stu-id="94795-104">Syntax</span></span>  
  
```cpp  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="94795-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="94795-105">Members</span></span>  
  
|<span data-ttu-id="94795-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="94795-106">Member</span></span>|<span data-ttu-id="94795-107">説明</span><span class="sxs-lookup"><span data-stu-id="94795-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="94795-108">変換先にファイルをコピーしないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="94795-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="94795-109">モジュールまたは複合イメージは、構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="94795-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="94795-110">モジュールまたは複合にクラスの参照があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="94795-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94795-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="94795-111">Requirements</span></span>  
 <span data-ttu-id="94795-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94795-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94795-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="94795-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94795-114">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="94795-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94795-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94795-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94795-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="94795-116">See also</span></span>

- [<span data-ttu-id="94795-117">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="94795-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

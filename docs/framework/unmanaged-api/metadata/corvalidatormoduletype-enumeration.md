---
title: CorValidatorModuleType 列挙型
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 14eee096c25967d321e4693b260501827d944a80
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154181"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="16ade-102">CorValidatorModuleType 列挙型</span><span class="sxs-lookup"><span data-stu-id="16ade-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="16ade-103">モジュールの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="16ade-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16ade-104">構文</span><span class="sxs-lookup"><span data-stu-id="16ade-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a><span data-ttu-id="16ade-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="16ade-105">Members</span></span>  
  
|<span data-ttu-id="16ade-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="16ade-106">Member</span></span>|<span data-ttu-id="16ade-107">説明</span><span class="sxs-lookup"><span data-stu-id="16ade-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="16ade-108">モジュールは、型が無効です。</span><span class="sxs-lookup"><span data-stu-id="16ade-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="16ade-109">最小値、`CorValidatorModuleType`列挙型。</span><span class="sxs-lookup"><span data-stu-id="16ade-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="16ade-110">モジュールは、ポータブル実行可能 (PE) ファイルです。</span><span class="sxs-lookup"><span data-stu-id="16ade-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="16ade-111">モジュールは、.obj ファイルです。</span><span class="sxs-lookup"><span data-stu-id="16ade-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="16ade-112">モジュールでは、デバッガーのエディット コンティニュ セッションです。</span><span class="sxs-lookup"><span data-stu-id="16ade-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="16ade-113">モジュールは、いずれかの段階的に構築されています。</span><span class="sxs-lookup"><span data-stu-id="16ade-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="16ade-114">最大値、`CorValidatorModuleType`列挙型。</span><span class="sxs-lookup"><span data-stu-id="16ade-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="16ade-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="16ade-115">Requirements</span></span>  
 <span data-ttu-id="16ade-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="16ade-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16ade-117">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="16ade-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="16ade-118">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="16ade-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="16ade-119">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="16ade-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="16ade-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="16ade-120">See also</span></span>

- [<span data-ttu-id="16ade-121">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="16ade-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

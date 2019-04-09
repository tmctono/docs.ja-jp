---
title: CorParamAttr 列挙型
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97f62b082db11a5f0bb930e33cb47acef76e7a04
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092059"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="c66ba-102">CorParamAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="c66ba-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="c66ba-103">メソッド パラメーターのメタデータを記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c66ba-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c66ba-104">構文</span><span class="sxs-lookup"><span data-stu-id="c66ba-104">Syntax</span></span>  
  
```  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="c66ba-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c66ba-105">Members</span></span>  
  
|<span data-ttu-id="c66ba-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c66ba-106">Member</span></span>|<span data-ttu-id="c66ba-107">説明</span><span class="sxs-lookup"><span data-stu-id="c66ba-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="c66ba-108">パラメーターがメソッドの呼び出しに渡されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="c66ba-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="c66ba-109">パラメーターが渡されること、メソッドから戻り値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c66ba-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="c66ba-110">パラメーターが省略可能なことを指定します。</span><span class="sxs-lookup"><span data-stu-id="c66ba-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="c66ba-111">共通言語ランタイムでは、内部使用のため予約されています。</span><span class="sxs-lookup"><span data-stu-id="c66ba-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="c66ba-112">パラメーターの既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c66ba-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="c66ba-113">パラメーターがマーシャ リング情報を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="c66ba-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="c66ba-114">使用されません。</span><span class="sxs-lookup"><span data-stu-id="c66ba-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c66ba-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="c66ba-115">Requirements</span></span>  
 <span data-ttu-id="c66ba-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c66ba-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c66ba-117">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c66ba-117">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="c66ba-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c66ba-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c66ba-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c66ba-119">See also</span></span>

- [<span data-ttu-id="c66ba-120">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="c66ba-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

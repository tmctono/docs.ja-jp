---
title: CorLocalRefPreservation 列挙型
ms.date: 03/30/2017
api_name:
- CorLocalRefPreservation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLocalRefPreservation
helpviewer_keywords:
- CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 845994b96445d8ec2a0e37affc5164b432894a91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045712"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="1c9ca-102">CorLocalRefPreservation 列挙型</span><span class="sxs-lookup"><span data-stu-id="1c9ca-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="1c9ca-103">ローカル参照の処理のためのフラグ値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="1c9ca-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c9ca-104">構文</span><span class="sxs-lookup"><span data-stu-id="1c9ca-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="1c9ca-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="1c9ca-105">Members</span></span>  
  
|<span data-ttu-id="1c9ca-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="1c9ca-106">Member</span></span>|<span data-ttu-id="1c9ca-107">説明</span><span class="sxs-lookup"><span data-stu-id="1c9ca-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="1c9ca-108">ローカルの参照を保存しません。</span><span class="sxs-lookup"><span data-stu-id="1c9ca-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="1c9ca-109">ローカル型の参照を保持します。</span><span class="sxs-lookup"><span data-stu-id="1c9ca-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="1c9ca-110">ローカル メンバーの参照を保持します。</span><span class="sxs-lookup"><span data-stu-id="1c9ca-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c9ca-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="1c9ca-111">Requirements</span></span>  
 <span data-ttu-id="1c9ca-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c9ca-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c9ca-113">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="1c9ca-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1c9ca-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c9ca-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c9ca-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c9ca-115">See also</span></span>

- [<span data-ttu-id="1c9ca-116">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="1c9ca-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

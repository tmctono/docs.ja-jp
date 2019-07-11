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
ms.openlocfilehash: 6338034d6714e8770e06ff61994fdf4433eb1684
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781788"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="02341-102">CorLocalRefPreservation 列挙型</span><span class="sxs-lookup"><span data-stu-id="02341-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="02341-103">ローカル参照の処理のためのフラグ値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="02341-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02341-104">構文</span><span class="sxs-lookup"><span data-stu-id="02341-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="02341-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="02341-105">Members</span></span>  
  
|<span data-ttu-id="02341-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="02341-106">Member</span></span>|<span data-ttu-id="02341-107">説明</span><span class="sxs-lookup"><span data-stu-id="02341-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="02341-108">ローカルの参照を保存しません。</span><span class="sxs-lookup"><span data-stu-id="02341-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="02341-109">ローカル型の参照を保持します。</span><span class="sxs-lookup"><span data-stu-id="02341-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="02341-110">ローカル メンバーの参照を保持します。</span><span class="sxs-lookup"><span data-stu-id="02341-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02341-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="02341-111">Requirements</span></span>  
 <span data-ttu-id="02341-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02341-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02341-113">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="02341-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="02341-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02341-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02341-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="02341-115">See also</span></span>

- [<span data-ttu-id="02341-116">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="02341-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

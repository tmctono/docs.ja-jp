---
title: _EFN_GetManagedObjectFieldInfo 関数
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
ms.openlocfilehash: 182424632e4f81dfdf86e87dc6bb2c75c2780fce
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793771"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="28a96-102">\_EFN\_GetManagedObjectFieldInfo 関数</span><span class="sxs-lookup"><span data-stu-id="28a96-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="28a96-103">指定したオブジェクト ポインターとフィールド名を使用して、オブジェクトの先頭からフィールドまでのオフセットとフィールドの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="28a96-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28a96-104">構文</span><span class="sxs-lookup"><span data-stu-id="28a96-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28a96-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="28a96-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="28a96-106">からデバッグクライアントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="28a96-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="28a96-107">からマネージオブジェクトポインター。</span><span class="sxs-lookup"><span data-stu-id="28a96-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="28a96-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="28a96-108">szFieldName</span></span>  
 <span data-ttu-id="28a96-109">からフィールド名へのマネージオブジェクトポインター。</span><span class="sxs-lookup"><span data-stu-id="28a96-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="28a96-110">入出力フィールド値。</span><span class="sxs-lookup"><span data-stu-id="28a96-110">[out] The field value.</span></span> <span data-ttu-id="28a96-111">このパラメーターは、null でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="28a96-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="28a96-112">入出力`objAddr` からフィールドへのオフセット。</span><span class="sxs-lookup"><span data-stu-id="28a96-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="28a96-113">このパラメーターは、null でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="28a96-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28a96-114">コメント</span><span class="sxs-lookup"><span data-stu-id="28a96-114">Remarks</span></span>  
 <span data-ttu-id="28a96-115">オフセットが0の場合、オフセットは書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="28a96-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="28a96-116">現在コンテキスト内にあるスレッドにマネージコードがない場合、関数は、ファシリティ値が0xa0 でエラーコードが0x1000 の HRESULT SOS_E_NOMANAGEDCODE を返します。</span><span class="sxs-lookup"><span data-stu-id="28a96-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28a96-117">要件</span><span class="sxs-lookup"><span data-stu-id="28a96-117">Requirements</span></span>  
 <span data-ttu-id="28a96-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a96-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28a96-119">**ヘッダー:** SOS_Stacktrace</span><span class="sxs-lookup"><span data-stu-id="28a96-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="28a96-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28a96-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a96-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="28a96-121">See also</span></span>

- [<span data-ttu-id="28a96-122">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="28a96-122">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)

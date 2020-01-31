---
title: ICorPublishAppDomain::GetName メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
ms.openlocfilehash: 4325d61d12a66b17f88e5e368cbbc7806d0a3ec5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790716"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="1bd59-102">ICorPublishAppDomain::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="1bd59-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="1bd59-103">この[ICorPublishAppDomain](icorpublishappdomain-interface.md)によって表されるアプリケーションドメインの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="1bd59-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bd59-104">構文</span><span class="sxs-lookup"><span data-stu-id="1bd59-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bd59-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1bd59-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="1bd59-106">[in] `szName` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="1bd59-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="1bd59-107">入出力`szName` 配列に返された、null 文字を含むワイド文字の数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1bd59-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="1bd59-108">入出力名前を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="1bd59-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bd59-109">コメント</span><span class="sxs-lookup"><span data-stu-id="1bd59-109">Remarks</span></span>  
 <span data-ttu-id="1bd59-110">`szName` が null 以外の場合、`GetName` メソッドは `szName`に最大 `cchName` 文字 (null ターミネータを含む) をコピーします。</span><span class="sxs-lookup"><span data-stu-id="1bd59-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="1bd59-111">`pcchName`で null 以外の値が返された場合、名前の実際の文字数 (null ターミネータを含む) が `szName` 配列に格納されます。</span><span class="sxs-lookup"><span data-stu-id="1bd59-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="1bd59-112">`GetName` メソッドは、コピーされた文字数に関係なく、S_OK HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="1bd59-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bd59-113">要件</span><span class="sxs-lookup"><span data-stu-id="1bd59-113">Requirements</span></span>  
 <span data-ttu-id="1bd59-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bd59-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bd59-115">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="1bd59-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1bd59-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bd59-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bd59-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bd59-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bd59-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bd59-118">See also</span></span>

- [<span data-ttu-id="1bd59-119">ICorPublishAppDomain インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1bd59-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)

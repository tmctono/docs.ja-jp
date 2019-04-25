---
title: ICeeGen::GetStringSection メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.GetStringSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef22114b582ebfc9714dedc0cb6e66594d945ca1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905347"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="7b567-102">ICeeGen::GetStringSection メソッド</span><span class="sxs-lookup"><span data-stu-id="7b567-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="7b567-103">指定したハンドルによって参照されるコードのセクションの文字列表現を取得します。</span><span class="sxs-lookup"><span data-stu-id="7b567-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="7b567-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b567-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b567-105">構文</span><span class="sxs-lookup"><span data-stu-id="7b567-105">Syntax</span></span>  
  
```  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b567-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7b567-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="7b567-107">[入力、出力]コード セクションへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="7b567-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b567-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="7b567-108">Requirements</span></span>  
 <span data-ttu-id="7b567-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b567-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b567-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7b567-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b567-111">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="7b567-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7b567-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b567-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b567-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b567-113">See also</span></span>

- [<span data-ttu-id="7b567-114">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7b567-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

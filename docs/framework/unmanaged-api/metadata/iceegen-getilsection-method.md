---
title: ICeeGen::GetIlSection メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIlSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8bddb782e13b4e7400c7e4a8128dc333efc8141d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746184"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="7fe5d-102">ICeeGen::GetIlSection メソッド</span><span class="sxs-lookup"><span data-stu-id="7fe5d-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="7fe5d-103">指定したハンドルによって参照される基本の中間言語コードのセクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="7fe5d-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="7fe5d-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fe5d-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fe5d-105">構文</span><span class="sxs-lookup"><span data-stu-id="7fe5d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fe5d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7fe5d-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="7fe5d-107">[in]取得するセクションへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="7fe5d-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fe5d-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="7fe5d-108">Requirements</span></span>  
 <span data-ttu-id="7fe5d-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fe5d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fe5d-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7fe5d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7fe5d-111">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="7fe5d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7fe5d-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fe5d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fe5d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fe5d-113">See also</span></span>

- [<span data-ttu-id="7fe5d-114">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7fe5d-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

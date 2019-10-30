---
title: ICorPublishProcess::GetDisplayName メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
ms.openlocfilehash: df2750f082ddc40bbeee121116c3e877d037da84
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140434"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="2ca30-102">ICorPublishProcess::GetDisplayName メソッド</span><span class="sxs-lookup"><span data-stu-id="2ca30-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="2ca30-103">この[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)によって参照されるプロセスの実行可能ファイルの完全パスを取得します。</span><span class="sxs-lookup"><span data-stu-id="2ca30-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ca30-104">構文</span><span class="sxs-lookup"><span data-stu-id="2ca30-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ca30-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ca30-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="2ca30-106">[in] `szName` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="2ca30-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2ca30-107">入出力`szName` 配列で返されるワイド文字数。</span><span class="sxs-lookup"><span data-stu-id="2ca30-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="2ca30-108">入出力実行可能ファイルの完全パスを含む、名前を格納する配列。</span><span class="sxs-lookup"><span data-stu-id="2ca30-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="2ca30-109">名前が null で終了しています。</span><span class="sxs-lookup"><span data-stu-id="2ca30-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ca30-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="2ca30-110">Requirements</span></span>  
 <span data-ttu-id="2ca30-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ca30-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ca30-112">**ヘッダー:** CorPub .idl、CorPub .h</span><span class="sxs-lookup"><span data-stu-id="2ca30-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2ca30-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ca30-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ca30-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ca30-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ca30-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ca30-115">See also</span></span>

- [<span data-ttu-id="2ca30-116">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ca30-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)

---
title: OLE DB スキーマ コレクション
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164685"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="48037-102">OLE DB スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="48037-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="48037-103">ここでは、Microsoft SQL Server、Oracle、および Microsoft Jet 用の各 OLE DB プロバイダーでのスキーマ コレクションのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="48037-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="48037-104">Microsoft SQL Server OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="48037-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="48037-105">Microsoft SQL Server OLE DB Driver は、共通のスキーマ コレクションに加えて次の特定のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="48037-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="48037-106">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="48037-106">Tables</span></span>  
  
-   <span data-ttu-id="48037-107">列</span><span class="sxs-lookup"><span data-stu-id="48037-107">Columns</span></span>  
  
-   <span data-ttu-id="48037-108">手順</span><span class="sxs-lookup"><span data-stu-id="48037-108">Procedures</span></span>  
  
-   <span data-ttu-id="48037-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="48037-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="48037-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="48037-110">Catalog</span></span>  
  
-   <span data-ttu-id="48037-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="48037-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="48037-112">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="48037-112">Tables</span></span>  
  
|<span data-ttu-id="48037-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-113">ColumnName</span></span>|<span data-ttu-id="48037-114">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-115">TABLE_CATALOG</span></span>|<span data-ttu-id="48037-116">String</span><span class="sxs-lookup"><span data-stu-id="48037-116">String</span></span>|  
|<span data-ttu-id="48037-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="48037-118">String</span><span class="sxs-lookup"><span data-stu-id="48037-118">String</span></span>|  
|<span data-ttu-id="48037-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-119">TABLE_NAME</span></span>|<span data-ttu-id="48037-120">String</span><span class="sxs-lookup"><span data-stu-id="48037-120">String</span></span>|  
|<span data-ttu-id="48037-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-121">TABLE_TYPE</span></span>|<span data-ttu-id="48037-122">String</span><span class="sxs-lookup"><span data-stu-id="48037-122">String</span></span>|  
|<span data-ttu-id="48037-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="48037-123">TABLE_GUID</span></span>|<span data-ttu-id="48037-124">Guid</span><span class="sxs-lookup"><span data-stu-id="48037-124">Guid</span></span>|  
|<span data-ttu-id="48037-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48037-125">DESCRIPTION</span></span>|<span data-ttu-id="48037-126">String</span><span class="sxs-lookup"><span data-stu-id="48037-126">String</span></span>|  
|<span data-ttu-id="48037-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="48037-127">TABLE_PROPID</span></span>|<span data-ttu-id="48037-128">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-128">Int64</span></span>|  
|<span data-ttu-id="48037-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="48037-129">DATE_CREATED</span></span>|<span data-ttu-id="48037-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-130">DateTime</span></span>|  
|<span data-ttu-id="48037-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="48037-131">DATE_MODIFIED</span></span>|<span data-ttu-id="48037-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="48037-133">列</span><span class="sxs-lookup"><span data-stu-id="48037-133">Columns</span></span>  
  
|<span data-ttu-id="48037-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-134">ColumnName</span></span>|<span data-ttu-id="48037-135">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-136">TABLE_CATALOG</span></span>|<span data-ttu-id="48037-137">String</span><span class="sxs-lookup"><span data-stu-id="48037-137">String</span></span>|  
|<span data-ttu-id="48037-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="48037-139">String</span><span class="sxs-lookup"><span data-stu-id="48037-139">String</span></span>|  
|<span data-ttu-id="48037-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-140">TABLE_NAME</span></span>|<span data-ttu-id="48037-141">String</span><span class="sxs-lookup"><span data-stu-id="48037-141">String</span></span>|  
|<span data-ttu-id="48037-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-142">COLUMN_NAME</span></span>|<span data-ttu-id="48037-143">String</span><span class="sxs-lookup"><span data-stu-id="48037-143">String</span></span>|  
|<span data-ttu-id="48037-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="48037-144">COLUMN_GUID</span></span>|<span data-ttu-id="48037-145">Guid</span><span class="sxs-lookup"><span data-stu-id="48037-145">Guid</span></span>|  
|<span data-ttu-id="48037-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="48037-146">COLUMN_PROPID</span></span>|<span data-ttu-id="48037-147">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-147">Int64</span></span>|  
|<span data-ttu-id="48037-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="48037-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="48037-149">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-149">Int64</span></span>|  
|<span data-ttu-id="48037-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="48037-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="48037-151">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-151">Boolean</span></span>|  
|<span data-ttu-id="48037-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="48037-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="48037-153">String</span><span class="sxs-lookup"><span data-stu-id="48037-153">String</span></span>|  
|<span data-ttu-id="48037-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="48037-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="48037-155">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-155">Int64</span></span>|  
|<span data-ttu-id="48037-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="48037-156">IS_NULLABLE</span></span>|<span data-ttu-id="48037-157">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-157">Boolean</span></span>|  
|<span data-ttu-id="48037-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-158">DATA_TYPE</span></span>|<span data-ttu-id="48037-159">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-159">Int32</span></span>|  
|<span data-ttu-id="48037-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="48037-160">TYPE_GUID</span></span>|<span data-ttu-id="48037-161">Guid</span><span class="sxs-lookup"><span data-stu-id="48037-161">Guid</span></span>|  
|<span data-ttu-id="48037-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="48037-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="48037-163">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-163">Int64</span></span>|  
|<span data-ttu-id="48037-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="48037-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="48037-165">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-165">Int64</span></span>|  
|<span data-ttu-id="48037-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="48037-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="48037-167">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-167">Int32</span></span>|  
|<span data-ttu-id="48037-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="48037-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="48037-169">Int16</span><span class="sxs-lookup"><span data-stu-id="48037-169">Int16</span></span>|  
|<span data-ttu-id="48037-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="48037-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="48037-171">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-171">Int64</span></span>|  
|<span data-ttu-id="48037-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="48037-173">String</span><span class="sxs-lookup"><span data-stu-id="48037-173">String</span></span>|  
|<span data-ttu-id="48037-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="48037-175">String</span><span class="sxs-lookup"><span data-stu-id="48037-175">String</span></span>|  
|<span data-ttu-id="48037-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="48037-177">String</span><span class="sxs-lookup"><span data-stu-id="48037-177">String</span></span>|  
|<span data-ttu-id="48037-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="48037-179">String</span><span class="sxs-lookup"><span data-stu-id="48037-179">String</span></span>|  
|<span data-ttu-id="48037-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="48037-181">String</span><span class="sxs-lookup"><span data-stu-id="48037-181">String</span></span>|  
|<span data-ttu-id="48037-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-182">COLLATION_NAME</span></span>|<span data-ttu-id="48037-183">String</span><span class="sxs-lookup"><span data-stu-id="48037-183">String</span></span>|  
|<span data-ttu-id="48037-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="48037-185">String</span><span class="sxs-lookup"><span data-stu-id="48037-185">String</span></span>|  
|<span data-ttu-id="48037-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="48037-187">String</span><span class="sxs-lookup"><span data-stu-id="48037-187">String</span></span>|  
|<span data-ttu-id="48037-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-188">DOMAIN_NAME</span></span>|<span data-ttu-id="48037-189">String</span><span class="sxs-lookup"><span data-stu-id="48037-189">String</span></span>|  
|<span data-ttu-id="48037-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48037-190">DESCRIPTION</span></span>|<span data-ttu-id="48037-191">String</span><span class="sxs-lookup"><span data-stu-id="48037-191">String</span></span>|  
|<span data-ttu-id="48037-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="48037-192">COLUMN_LCID</span></span>|<span data-ttu-id="48037-193">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-193">Int32</span></span>|  
|<span data-ttu-id="48037-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="48037-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="48037-195">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-195">Int32</span></span>|  
|<span data-ttu-id="48037-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="48037-196">COLUMN_SORTID</span></span>|<span data-ttu-id="48037-197">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-197">Int32</span></span>|  
|<span data-ttu-id="48037-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="48037-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="48037-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="48037-199">Byte[]</span></span>|  
|<span data-ttu-id="48037-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="48037-200">IS_COMPUTED</span></span>|<span data-ttu-id="48037-201">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="48037-202">手順</span><span class="sxs-lookup"><span data-stu-id="48037-202">Procedures</span></span>  
  
|<span data-ttu-id="48037-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-203">ColumnName</span></span>|<span data-ttu-id="48037-204">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="48037-206">String</span><span class="sxs-lookup"><span data-stu-id="48037-206">String</span></span>|  
|<span data-ttu-id="48037-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="48037-208">String</span><span class="sxs-lookup"><span data-stu-id="48037-208">String</span></span>|  
|<span data-ttu-id="48037-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="48037-210">String</span><span class="sxs-lookup"><span data-stu-id="48037-210">String</span></span>|  
|<span data-ttu-id="48037-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="48037-212">Int16</span><span class="sxs-lookup"><span data-stu-id="48037-212">Int16</span></span>|  
|<span data-ttu-id="48037-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="48037-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="48037-214">String</span><span class="sxs-lookup"><span data-stu-id="48037-214">String</span></span>|  
|<span data-ttu-id="48037-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48037-215">DESCRIPTION</span></span>|<span data-ttu-id="48037-216">String</span><span class="sxs-lookup"><span data-stu-id="48037-216">String</span></span>|  
|<span data-ttu-id="48037-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="48037-217">DATE_CREATED</span></span>|<span data-ttu-id="48037-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-218">DateTime</span></span>|  
|<span data-ttu-id="48037-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="48037-219">DATE_MODIFIED</span></span>|<span data-ttu-id="48037-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="48037-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="48037-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="48037-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-222">ColumnName</span></span>|<span data-ttu-id="48037-223">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="48037-225">String</span><span class="sxs-lookup"><span data-stu-id="48037-225">String</span></span>|  
|<span data-ttu-id="48037-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="48037-227">String</span><span class="sxs-lookup"><span data-stu-id="48037-227">String</span></span>|  
|<span data-ttu-id="48037-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="48037-229">String</span><span class="sxs-lookup"><span data-stu-id="48037-229">String</span></span>|  
|<span data-ttu-id="48037-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-230">PARAMETER_NAME</span></span>|<span data-ttu-id="48037-231">String</span><span class="sxs-lookup"><span data-stu-id="48037-231">String</span></span>|  
|<span data-ttu-id="48037-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="48037-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="48037-233">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-233">Int32</span></span>|  
|<span data-ttu-id="48037-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="48037-235">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-235">Int32</span></span>|  
|<span data-ttu-id="48037-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="48037-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="48037-237">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-237">Boolean</span></span>|  
|<span data-ttu-id="48037-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="48037-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="48037-239">String</span><span class="sxs-lookup"><span data-stu-id="48037-239">String</span></span>|  
|<span data-ttu-id="48037-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="48037-240">IS_NULLABLE</span></span>|<span data-ttu-id="48037-241">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-241">Boolean</span></span>|  
|<span data-ttu-id="48037-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-242">DATA_TYPE</span></span>|<span data-ttu-id="48037-243">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-243">Int32</span></span>|  
|<span data-ttu-id="48037-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="48037-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="48037-245">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-245">Int64</span></span>|  
|<span data-ttu-id="48037-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="48037-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="48037-247">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-247">Int64</span></span>|  
|<span data-ttu-id="48037-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="48037-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="48037-249">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-249">Int32</span></span>|  
|<span data-ttu-id="48037-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="48037-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="48037-251">Int16</span><span class="sxs-lookup"><span data-stu-id="48037-251">Int16</span></span>|  
|<span data-ttu-id="48037-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48037-252">DESCRIPTION</span></span>|<span data-ttu-id="48037-253">String</span><span class="sxs-lookup"><span data-stu-id="48037-253">String</span></span>|  
|<span data-ttu-id="48037-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-254">TYPE_NAME</span></span>|<span data-ttu-id="48037-255">String</span><span class="sxs-lookup"><span data-stu-id="48037-255">String</span></span>|  
|<span data-ttu-id="48037-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="48037-257">String</span><span class="sxs-lookup"><span data-stu-id="48037-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="48037-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="48037-258">Catalog</span></span>  
  
|<span data-ttu-id="48037-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-259">ColumnName</span></span>|<span data-ttu-id="48037-260">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-261">CATALOG_NAME</span></span>|<span data-ttu-id="48037-262">String</span><span class="sxs-lookup"><span data-stu-id="48037-262">String</span></span>|  
|<span data-ttu-id="48037-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48037-263">DESCRIPTION</span></span>|<span data-ttu-id="48037-264">String</span><span class="sxs-lookup"><span data-stu-id="48037-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="48037-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="48037-265">Indexes</span></span>  
  
|<span data-ttu-id="48037-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-266">ColumnName</span></span>|<span data-ttu-id="48037-267">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-268">TABLE_CATALOG</span></span>|<span data-ttu-id="48037-269">String</span><span class="sxs-lookup"><span data-stu-id="48037-269">String</span></span>|  
|<span data-ttu-id="48037-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="48037-271">String</span><span class="sxs-lookup"><span data-stu-id="48037-271">String</span></span>|  
|<span data-ttu-id="48037-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-272">TABLE_NAME</span></span>|<span data-ttu-id="48037-273">String</span><span class="sxs-lookup"><span data-stu-id="48037-273">String</span></span>|  
|<span data-ttu-id="48037-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-274">INDEX_CATALOG</span></span>|<span data-ttu-id="48037-275">String</span><span class="sxs-lookup"><span data-stu-id="48037-275">String</span></span>|  
|<span data-ttu-id="48037-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="48037-277">String</span><span class="sxs-lookup"><span data-stu-id="48037-277">String</span></span>|  
|<span data-ttu-id="48037-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-278">INDEX_NAME</span></span>|<span data-ttu-id="48037-279">String</span><span class="sxs-lookup"><span data-stu-id="48037-279">String</span></span>|  
|<span data-ttu-id="48037-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="48037-280">PRIMARY_KEY</span></span>|<span data-ttu-id="48037-281">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-281">Boolean</span></span>|  
|<span data-ttu-id="48037-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="48037-282">UNIQUE</span></span>|<span data-ttu-id="48037-283">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-283">Boolean</span></span>|  
|<span data-ttu-id="48037-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="48037-284">CLUSTERED</span></span>|<span data-ttu-id="48037-285">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-285">Boolean</span></span>|  
|<span data-ttu-id="48037-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-286">TYPE</span></span>|<span data-ttu-id="48037-287">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-287">Int32</span></span>|  
|<span data-ttu-id="48037-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="48037-288">FILL_FACTOR</span></span>|<span data-ttu-id="48037-289">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-289">Int32</span></span>|  
|<span data-ttu-id="48037-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="48037-290">INITIAL_SIZE</span></span>|<span data-ttu-id="48037-291">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-291">Int32</span></span>|  
|<span data-ttu-id="48037-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="48037-292">NULLS</span></span>|<span data-ttu-id="48037-293">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-293">Int32</span></span>|  
|<span data-ttu-id="48037-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="48037-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="48037-295">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-295">Boolean</span></span>|  
|<span data-ttu-id="48037-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="48037-296">AUTO_UPDATE</span></span>|<span data-ttu-id="48037-297">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-297">Boolean</span></span>|  
|<span data-ttu-id="48037-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="48037-298">NULL_COLLATION</span></span>|<span data-ttu-id="48037-299">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-299">Int32</span></span>|  
|<span data-ttu-id="48037-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="48037-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="48037-301">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-301">Int64</span></span>|  
|<span data-ttu-id="48037-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-302">COLUMN_NAME</span></span>|<span data-ttu-id="48037-303">String</span><span class="sxs-lookup"><span data-stu-id="48037-303">String</span></span>|  
|<span data-ttu-id="48037-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="48037-304">COLUMN_GUID</span></span>|<span data-ttu-id="48037-305">Guid</span><span class="sxs-lookup"><span data-stu-id="48037-305">Guid</span></span>|  
|<span data-ttu-id="48037-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="48037-306">COLUMN_PROPID</span></span>|<span data-ttu-id="48037-307">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-307">Int64</span></span>|  
|<span data-ttu-id="48037-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="48037-308">COLLATION</span></span>|<span data-ttu-id="48037-309">Int16</span><span class="sxs-lookup"><span data-stu-id="48037-309">Int16</span></span>|  
|<span data-ttu-id="48037-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="48037-310">CARDINALITY</span></span>|<span data-ttu-id="48037-311">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="48037-311">Decimal</span></span>|  
|<span data-ttu-id="48037-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="48037-312">PAGES</span></span>|<span data-ttu-id="48037-313">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-313">Int32</span></span>|  
|<span data-ttu-id="48037-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="48037-314">FILTER_CONDITION</span></span>|<span data-ttu-id="48037-315">String</span><span class="sxs-lookup"><span data-stu-id="48037-315">String</span></span>|  
|<span data-ttu-id="48037-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="48037-316">INTEGRATED</span></span>|<span data-ttu-id="48037-317">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="48037-318">Microsoft Oracle OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="48037-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="48037-319">Microsoft Oracle OLE DB Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="48037-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="48037-320">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="48037-320">Tables</span></span>  
  
-   <span data-ttu-id="48037-321">列</span><span class="sxs-lookup"><span data-stu-id="48037-321">Columns</span></span>  
  
-   <span data-ttu-id="48037-322">手順</span><span class="sxs-lookup"><span data-stu-id="48037-322">Procedures</span></span>  
  
-   <span data-ttu-id="48037-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="48037-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="48037-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="48037-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="48037-325">Views</span><span class="sxs-lookup"><span data-stu-id="48037-325">Views</span></span>  
  
-   <span data-ttu-id="48037-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="48037-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="48037-327">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="48037-327">Tables</span></span>  
  
|<span data-ttu-id="48037-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-328">ColumnName</span></span>|<span data-ttu-id="48037-329">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-330">TABLE_CATALOG</span></span>|<span data-ttu-id="48037-331">String</span><span class="sxs-lookup"><span data-stu-id="48037-331">String</span></span>|  
|<span data-ttu-id="48037-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="48037-333">String</span><span class="sxs-lookup"><span data-stu-id="48037-333">String</span></span>|  
|<span data-ttu-id="48037-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-334">TABLE_NAME</span></span>|<span data-ttu-id="48037-335">String</span><span class="sxs-lookup"><span data-stu-id="48037-335">String</span></span>|  
|<span data-ttu-id="48037-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-336">TABLE_TYPE</span></span>|<span data-ttu-id="48037-337">String</span><span class="sxs-lookup"><span data-stu-id="48037-337">String</span></span>|  
|<span data-ttu-id="48037-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="48037-338">TABLE_GUID</span></span>|<span data-ttu-id="48037-339">Guid</span><span class="sxs-lookup"><span data-stu-id="48037-339">Guid</span></span>|  
|<span data-ttu-id="48037-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48037-340">DESCRIPTION</span></span>|<span data-ttu-id="48037-341">String</span><span class="sxs-lookup"><span data-stu-id="48037-341">String</span></span>|  
|<span data-ttu-id="48037-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="48037-342">TABLE_PROPID</span></span>|<span data-ttu-id="48037-343">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-343">Int64</span></span>|  
|<span data-ttu-id="48037-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="48037-344">DATE_CREATED</span></span>|<span data-ttu-id="48037-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-345">DateTime</span></span>|  
|<span data-ttu-id="48037-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="48037-346">DATE_MODIFIED</span></span>|<span data-ttu-id="48037-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="48037-348">列</span><span class="sxs-lookup"><span data-stu-id="48037-348">Columns</span></span>  
  
|<span data-ttu-id="48037-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-349">ColumnName</span></span>|<span data-ttu-id="48037-350">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-351">TABLE_CATALOG</span></span>|<span data-ttu-id="48037-352">String</span><span class="sxs-lookup"><span data-stu-id="48037-352">String</span></span>|  
|<span data-ttu-id="48037-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="48037-354">String</span><span class="sxs-lookup"><span data-stu-id="48037-354">String</span></span>|  
|<span data-ttu-id="48037-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-355">TABLE_NAME</span></span>|<span data-ttu-id="48037-356">String</span><span class="sxs-lookup"><span data-stu-id="48037-356">String</span></span>|  
|<span data-ttu-id="48037-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-357">COLUMN_NAME</span></span>|<span data-ttu-id="48037-358">String</span><span class="sxs-lookup"><span data-stu-id="48037-358">String</span></span>|  
|<span data-ttu-id="48037-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="48037-359">COLUMN_GUID</span></span>|<span data-ttu-id="48037-360">Guid</span><span class="sxs-lookup"><span data-stu-id="48037-360">Guid</span></span>|  
|<span data-ttu-id="48037-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="48037-361">COLUMN_PROPID</span></span>|<span data-ttu-id="48037-362">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-362">Int64</span></span>|  
|<span data-ttu-id="48037-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="48037-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="48037-364">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-364">Int64</span></span>|  
|<span data-ttu-id="48037-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="48037-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="48037-366">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-366">Boolean</span></span>|  
|<span data-ttu-id="48037-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="48037-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="48037-368">String</span><span class="sxs-lookup"><span data-stu-id="48037-368">String</span></span>|  
|<span data-ttu-id="48037-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="48037-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="48037-370">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-370">Int64</span></span>|  
|<span data-ttu-id="48037-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="48037-371">IS_NULLABLE</span></span>|<span data-ttu-id="48037-372">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-372">Boolean</span></span>|  
|<span data-ttu-id="48037-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-373">DATA_TYPE</span></span>|<span data-ttu-id="48037-374">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-374">Int32</span></span>|  
|<span data-ttu-id="48037-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="48037-375">TYPE_GUID</span></span>|<span data-ttu-id="48037-376">Guid</span><span class="sxs-lookup"><span data-stu-id="48037-376">Guid</span></span>|  
|<span data-ttu-id="48037-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="48037-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="48037-378">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-378">Int64</span></span>|  
|<span data-ttu-id="48037-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="48037-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="48037-380">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-380">Int64</span></span>|  
|<span data-ttu-id="48037-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="48037-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="48037-382">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-382">Int32</span></span>|  
|<span data-ttu-id="48037-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="48037-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="48037-384">Int16</span><span class="sxs-lookup"><span data-stu-id="48037-384">Int16</span></span>|  
|<span data-ttu-id="48037-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="48037-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="48037-386">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-386">Int64</span></span>|  
|<span data-ttu-id="48037-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="48037-388">String</span><span class="sxs-lookup"><span data-stu-id="48037-388">String</span></span>|  
|<span data-ttu-id="48037-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="48037-390">String</span><span class="sxs-lookup"><span data-stu-id="48037-390">String</span></span>|  
|<span data-ttu-id="48037-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="48037-392">String</span><span class="sxs-lookup"><span data-stu-id="48037-392">String</span></span>|  
|<span data-ttu-id="48037-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="48037-394">String</span><span class="sxs-lookup"><span data-stu-id="48037-394">String</span></span>|  
|<span data-ttu-id="48037-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="48037-396">String</span><span class="sxs-lookup"><span data-stu-id="48037-396">String</span></span>|  
|<span data-ttu-id="48037-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-397">COLLATION_NAME</span></span>|<span data-ttu-id="48037-398">String</span><span class="sxs-lookup"><span data-stu-id="48037-398">String</span></span>|  
|<span data-ttu-id="48037-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="48037-400">String</span><span class="sxs-lookup"><span data-stu-id="48037-400">String</span></span>|  
|<span data-ttu-id="48037-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="48037-402">String</span><span class="sxs-lookup"><span data-stu-id="48037-402">String</span></span>|  
|<span data-ttu-id="48037-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-403">DOMAIN_NAME</span></span>|<span data-ttu-id="48037-404">String</span><span class="sxs-lookup"><span data-stu-id="48037-404">String</span></span>|  
|<span data-ttu-id="48037-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48037-405">DESCRIPTION</span></span>|<span data-ttu-id="48037-406">String</span><span class="sxs-lookup"><span data-stu-id="48037-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="48037-407">手順</span><span class="sxs-lookup"><span data-stu-id="48037-407">Procedures</span></span>  
  
|<span data-ttu-id="48037-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-408">ColumnName</span></span>|<span data-ttu-id="48037-409">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="48037-411">String</span><span class="sxs-lookup"><span data-stu-id="48037-411">String</span></span>|  
|<span data-ttu-id="48037-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="48037-413">String</span><span class="sxs-lookup"><span data-stu-id="48037-413">String</span></span>|  
|<span data-ttu-id="48037-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="48037-415">String</span><span class="sxs-lookup"><span data-stu-id="48037-415">String</span></span>|  
|<span data-ttu-id="48037-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="48037-417">Int16</span><span class="sxs-lookup"><span data-stu-id="48037-417">Int16</span></span>|  
|<span data-ttu-id="48037-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="48037-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="48037-419">String</span><span class="sxs-lookup"><span data-stu-id="48037-419">String</span></span>|  
|<span data-ttu-id="48037-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48037-420">DESCRIPTION</span></span>|<span data-ttu-id="48037-421">String</span><span class="sxs-lookup"><span data-stu-id="48037-421">String</span></span>|  
|<span data-ttu-id="48037-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="48037-422">DATE_CREATED</span></span>|<span data-ttu-id="48037-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-423">DateTime</span></span>|  
|<span data-ttu-id="48037-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="48037-424">DATE_MODIFIED</span></span>|<span data-ttu-id="48037-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="48037-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="48037-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="48037-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-427">ColumnName</span></span>|<span data-ttu-id="48037-428">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="48037-430">String</span><span class="sxs-lookup"><span data-stu-id="48037-430">String</span></span>|  
|<span data-ttu-id="48037-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="48037-432">String</span><span class="sxs-lookup"><span data-stu-id="48037-432">String</span></span>|  
|<span data-ttu-id="48037-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="48037-434">String</span><span class="sxs-lookup"><span data-stu-id="48037-434">String</span></span>|  
|<span data-ttu-id="48037-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-435">COLUMN_NAME</span></span>|<span data-ttu-id="48037-436">String</span><span class="sxs-lookup"><span data-stu-id="48037-436">String</span></span>|  
|<span data-ttu-id="48037-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="48037-437">COLUMN_GUID</span></span>|<span data-ttu-id="48037-438">Guid</span><span class="sxs-lookup"><span data-stu-id="48037-438">Guid</span></span>|  
|<span data-ttu-id="48037-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="48037-439">COLUMN_PROPID</span></span>|<span data-ttu-id="48037-440">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-440">Int64</span></span>|  
|<span data-ttu-id="48037-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="48037-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="48037-442">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-442">Int64</span></span>|  
|<span data-ttu-id="48037-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="48037-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="48037-444">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-444">Int64</span></span>|  
|<span data-ttu-id="48037-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="48037-445">IS_NULLABLE</span></span>|<span data-ttu-id="48037-446">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-446">Boolean</span></span>|  
|<span data-ttu-id="48037-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-447">DATA_TYPE</span></span>|<span data-ttu-id="48037-448">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-448">Int32</span></span>|  
|<span data-ttu-id="48037-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="48037-449">TYPE_GUID</span></span>|<span data-ttu-id="48037-450">Guid</span><span class="sxs-lookup"><span data-stu-id="48037-450">Guid</span></span>|  
|<span data-ttu-id="48037-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="48037-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="48037-452">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-452">Int64</span></span>|  
|<span data-ttu-id="48037-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="48037-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="48037-454">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-454">Int64</span></span>|  
|<span data-ttu-id="48037-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="48037-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="48037-456">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-456">Int32</span></span>|  
|<span data-ttu-id="48037-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="48037-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="48037-458">Int16</span><span class="sxs-lookup"><span data-stu-id="48037-458">Int16</span></span>|  
|<span data-ttu-id="48037-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48037-459">DESCRIPTION</span></span>|<span data-ttu-id="48037-460">String</span><span class="sxs-lookup"><span data-stu-id="48037-460">String</span></span>|  
|<span data-ttu-id="48037-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="48037-461">OVERLOAD</span></span>|<span data-ttu-id="48037-462">Int16</span><span class="sxs-lookup"><span data-stu-id="48037-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="48037-463">Views</span><span class="sxs-lookup"><span data-stu-id="48037-463">Views</span></span>  
  
|<span data-ttu-id="48037-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-464">ColumnName</span></span>|<span data-ttu-id="48037-465">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-466">TABLE_CATALOG</span></span>|<span data-ttu-id="48037-467">String</span><span class="sxs-lookup"><span data-stu-id="48037-467">String</span></span>|  
|<span data-ttu-id="48037-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="48037-469">String</span><span class="sxs-lookup"><span data-stu-id="48037-469">String</span></span>|  
|<span data-ttu-id="48037-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-470">TABLE_NAME</span></span>|<span data-ttu-id="48037-471">String</span><span class="sxs-lookup"><span data-stu-id="48037-471">String</span></span>|  
|<span data-ttu-id="48037-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="48037-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="48037-473">String</span><span class="sxs-lookup"><span data-stu-id="48037-473">String</span></span>|  
|<span data-ttu-id="48037-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="48037-474">CHECK_OPTION</span></span>|<span data-ttu-id="48037-475">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-475">Boolean</span></span>|  
|<span data-ttu-id="48037-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="48037-476">IS_UPDATABLE</span></span>|<span data-ttu-id="48037-477">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-477">Boolean</span></span>|  
|<span data-ttu-id="48037-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48037-478">DESCRIPTION</span></span>|<span data-ttu-id="48037-479">String</span><span class="sxs-lookup"><span data-stu-id="48037-479">String</span></span>|  
|<span data-ttu-id="48037-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="48037-480">DATE_CREATED</span></span>|<span data-ttu-id="48037-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-481">DateTime</span></span>|  
|<span data-ttu-id="48037-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="48037-482">DATE_MODIFIED</span></span>|<span data-ttu-id="48037-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="48037-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="48037-484">Indexes</span></span>  
  
|<span data-ttu-id="48037-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-485">ColumnName</span></span>|<span data-ttu-id="48037-486">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-487">TABLE_CATALOG</span></span>|<span data-ttu-id="48037-488">String</span><span class="sxs-lookup"><span data-stu-id="48037-488">String</span></span>|  
|<span data-ttu-id="48037-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="48037-490">String</span><span class="sxs-lookup"><span data-stu-id="48037-490">String</span></span>|  
|<span data-ttu-id="48037-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-491">TABLE_NAME</span></span>|<span data-ttu-id="48037-492">String</span><span class="sxs-lookup"><span data-stu-id="48037-492">String</span></span>|  
|<span data-ttu-id="48037-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-493">INDEX_CATALOG</span></span>|<span data-ttu-id="48037-494">String</span><span class="sxs-lookup"><span data-stu-id="48037-494">String</span></span>|  
|<span data-ttu-id="48037-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="48037-496">String</span><span class="sxs-lookup"><span data-stu-id="48037-496">String</span></span>|  
|<span data-ttu-id="48037-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-497">INDEX_NAME</span></span>|<span data-ttu-id="48037-498">String</span><span class="sxs-lookup"><span data-stu-id="48037-498">String</span></span>|  
|<span data-ttu-id="48037-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="48037-499">PRIMARY_KEY</span></span>|<span data-ttu-id="48037-500">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-500">Boolean</span></span>|  
|<span data-ttu-id="48037-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="48037-501">UNIQUE</span></span>|<span data-ttu-id="48037-502">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-502">Boolean</span></span>|  
|<span data-ttu-id="48037-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="48037-503">CLUSTERED</span></span>|<span data-ttu-id="48037-504">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-504">Boolean</span></span>|  
|<span data-ttu-id="48037-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-505">TYPE</span></span>|<span data-ttu-id="48037-506">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-506">Int32</span></span>|  
|<span data-ttu-id="48037-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="48037-507">FILL_FACTOR</span></span>|<span data-ttu-id="48037-508">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-508">Int32</span></span>|  
|<span data-ttu-id="48037-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="48037-509">INITIAL_SIZE</span></span>|<span data-ttu-id="48037-510">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-510">Int32</span></span>|  
|<span data-ttu-id="48037-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="48037-511">NULLS</span></span>|<span data-ttu-id="48037-512">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-512">Int32</span></span>|  
|<span data-ttu-id="48037-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="48037-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="48037-514">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-514">Boolean</span></span>|  
|<span data-ttu-id="48037-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="48037-515">AUTO_UPDATE</span></span>|<span data-ttu-id="48037-516">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-516">Boolean</span></span>|  
|<span data-ttu-id="48037-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="48037-517">NULL_COLLATION</span></span>|<span data-ttu-id="48037-518">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-518">Int32</span></span>|  
|<span data-ttu-id="48037-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="48037-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="48037-520">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-520">Int64</span></span>|  
|<span data-ttu-id="48037-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-521">COLUMN_NAME</span></span>|<span data-ttu-id="48037-522">String</span><span class="sxs-lookup"><span data-stu-id="48037-522">String</span></span>|  
|<span data-ttu-id="48037-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="48037-523">COLUMN_GUID</span></span>|<span data-ttu-id="48037-524">Guid</span><span class="sxs-lookup"><span data-stu-id="48037-524">Guid</span></span>|  
|<span data-ttu-id="48037-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="48037-525">COLUMN_PROPID</span></span>|<span data-ttu-id="48037-526">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-526">Int64</span></span>|  
|<span data-ttu-id="48037-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="48037-527">COLLATION</span></span>|<span data-ttu-id="48037-528">Int16</span><span class="sxs-lookup"><span data-stu-id="48037-528">Int16</span></span>|  
|<span data-ttu-id="48037-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="48037-529">CARDINALITY</span></span>|<span data-ttu-id="48037-530">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="48037-530">Decimal</span></span>|  
|<span data-ttu-id="48037-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="48037-531">PAGES</span></span>|<span data-ttu-id="48037-532">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-532">Int32</span></span>|  
|<span data-ttu-id="48037-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="48037-533">FILTER_CONDITION</span></span>|<span data-ttu-id="48037-534">String</span><span class="sxs-lookup"><span data-stu-id="48037-534">String</span></span>|  
|<span data-ttu-id="48037-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="48037-535">INTEGRATED</span></span>|<span data-ttu-id="48037-536">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="48037-537">Microsoft Jet OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="48037-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="48037-538">Microsoft Jet OLE DB Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="48037-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="48037-539">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="48037-539">Tables</span></span>  
  
-   <span data-ttu-id="48037-540">列</span><span class="sxs-lookup"><span data-stu-id="48037-540">Columns</span></span>  
  
-   <span data-ttu-id="48037-541">手順</span><span class="sxs-lookup"><span data-stu-id="48037-541">Procedures</span></span>  
  
-   <span data-ttu-id="48037-542">Views</span><span class="sxs-lookup"><span data-stu-id="48037-542">Views</span></span>  
  
-   <span data-ttu-id="48037-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="48037-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="48037-544">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="48037-544">Tables</span></span>  
  
|<span data-ttu-id="48037-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-545">ColumnName</span></span>|<span data-ttu-id="48037-546">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-547">TABLE_CATALOG</span></span>|<span data-ttu-id="48037-548">String</span><span class="sxs-lookup"><span data-stu-id="48037-548">String</span></span>|  
|<span data-ttu-id="48037-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="48037-550">String</span><span class="sxs-lookup"><span data-stu-id="48037-550">String</span></span>|  
|<span data-ttu-id="48037-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-551">TABLE_NAME</span></span>|<span data-ttu-id="48037-552">String</span><span class="sxs-lookup"><span data-stu-id="48037-552">String</span></span>|  
|<span data-ttu-id="48037-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-553">TABLE_TYPE</span></span>|<span data-ttu-id="48037-554">String</span><span class="sxs-lookup"><span data-stu-id="48037-554">String</span></span>|  
|<span data-ttu-id="48037-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="48037-555">TABLE_GUID</span></span>|<span data-ttu-id="48037-556">Guid</span><span class="sxs-lookup"><span data-stu-id="48037-556">Guid</span></span>|  
|<span data-ttu-id="48037-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48037-557">DESCRIPTION</span></span>|<span data-ttu-id="48037-558">String</span><span class="sxs-lookup"><span data-stu-id="48037-558">String</span></span>|  
|<span data-ttu-id="48037-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="48037-559">TABLE_PROPID</span></span>|<span data-ttu-id="48037-560">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-560">Int64</span></span>|  
|<span data-ttu-id="48037-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="48037-561">DATE_CREATED</span></span>|<span data-ttu-id="48037-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-562">DateTime</span></span>|  
|<span data-ttu-id="48037-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="48037-563">DATE_MODIFIED</span></span>|<span data-ttu-id="48037-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="48037-565">列</span><span class="sxs-lookup"><span data-stu-id="48037-565">Columns</span></span>  
  
|<span data-ttu-id="48037-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-566">ColumnName</span></span>|<span data-ttu-id="48037-567">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-568">TABLE_CATALOG</span></span>|<span data-ttu-id="48037-569">String</span><span class="sxs-lookup"><span data-stu-id="48037-569">String</span></span>|  
|<span data-ttu-id="48037-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="48037-571">String</span><span class="sxs-lookup"><span data-stu-id="48037-571">String</span></span>|  
|<span data-ttu-id="48037-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-572">TABLE_NAME</span></span>|<span data-ttu-id="48037-573">String</span><span class="sxs-lookup"><span data-stu-id="48037-573">String</span></span>|  
|<span data-ttu-id="48037-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-574">COLUMN_NAME</span></span>|<span data-ttu-id="48037-575">String</span><span class="sxs-lookup"><span data-stu-id="48037-575">String</span></span>|  
|<span data-ttu-id="48037-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="48037-576">COLUMN_GUID</span></span>|<span data-ttu-id="48037-577">Guid</span><span class="sxs-lookup"><span data-stu-id="48037-577">Guid</span></span>|  
|<span data-ttu-id="48037-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="48037-578">COLUMN_PROPID</span></span>|<span data-ttu-id="48037-579">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-579">Int64</span></span>|  
|<span data-ttu-id="48037-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="48037-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="48037-581">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-581">Int64</span></span>|  
|<span data-ttu-id="48037-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="48037-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="48037-583">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-583">Boolean</span></span>|  
|<span data-ttu-id="48037-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="48037-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="48037-585">String</span><span class="sxs-lookup"><span data-stu-id="48037-585">String</span></span>|  
|<span data-ttu-id="48037-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="48037-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="48037-587">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-587">Int64</span></span>|  
|<span data-ttu-id="48037-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="48037-588">IS_NULLABLE</span></span>|<span data-ttu-id="48037-589">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-589">Boolean</span></span>|  
|<span data-ttu-id="48037-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-590">DATA_TYPE</span></span>|<span data-ttu-id="48037-591">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-591">Int32</span></span>|  
|<span data-ttu-id="48037-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="48037-592">TYPE_GUID</span></span>|<span data-ttu-id="48037-593">Guid</span><span class="sxs-lookup"><span data-stu-id="48037-593">Guid</span></span>|  
|<span data-ttu-id="48037-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="48037-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="48037-595">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-595">Int64</span></span>|  
|<span data-ttu-id="48037-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="48037-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="48037-597">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-597">Int64</span></span>|  
|<span data-ttu-id="48037-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="48037-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="48037-599">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-599">Int32</span></span>|  
|<span data-ttu-id="48037-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="48037-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="48037-601">Int16</span><span class="sxs-lookup"><span data-stu-id="48037-601">Int16</span></span>|  
|<span data-ttu-id="48037-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="48037-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="48037-603">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-603">Int64</span></span>|  
|<span data-ttu-id="48037-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="48037-605">String</span><span class="sxs-lookup"><span data-stu-id="48037-605">String</span></span>|  
|<span data-ttu-id="48037-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="48037-607">String</span><span class="sxs-lookup"><span data-stu-id="48037-607">String</span></span>|  
|<span data-ttu-id="48037-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="48037-609">String</span><span class="sxs-lookup"><span data-stu-id="48037-609">String</span></span>|  
|<span data-ttu-id="48037-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="48037-611">String</span><span class="sxs-lookup"><span data-stu-id="48037-611">String</span></span>|  
|<span data-ttu-id="48037-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="48037-613">String</span><span class="sxs-lookup"><span data-stu-id="48037-613">String</span></span>|  
|<span data-ttu-id="48037-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-614">COLLATION_NAME</span></span>|<span data-ttu-id="48037-615">String</span><span class="sxs-lookup"><span data-stu-id="48037-615">String</span></span>|  
|<span data-ttu-id="48037-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="48037-617">String</span><span class="sxs-lookup"><span data-stu-id="48037-617">String</span></span>|  
|<span data-ttu-id="48037-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="48037-619">String</span><span class="sxs-lookup"><span data-stu-id="48037-619">String</span></span>|  
|<span data-ttu-id="48037-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-620">DOMAIN_NAME</span></span>|<span data-ttu-id="48037-621">String</span><span class="sxs-lookup"><span data-stu-id="48037-621">String</span></span>|  
|<span data-ttu-id="48037-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48037-622">DESCRIPTION</span></span>|<span data-ttu-id="48037-623">String</span><span class="sxs-lookup"><span data-stu-id="48037-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="48037-624">手順</span><span class="sxs-lookup"><span data-stu-id="48037-624">Procedures</span></span>  
  
|<span data-ttu-id="48037-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-625">ColumnName</span></span>|<span data-ttu-id="48037-626">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="48037-628">String</span><span class="sxs-lookup"><span data-stu-id="48037-628">String</span></span>|  
|<span data-ttu-id="48037-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="48037-630">String</span><span class="sxs-lookup"><span data-stu-id="48037-630">String</span></span>|  
|<span data-ttu-id="48037-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="48037-632">String</span><span class="sxs-lookup"><span data-stu-id="48037-632">String</span></span>|  
|<span data-ttu-id="48037-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="48037-634">Int16</span><span class="sxs-lookup"><span data-stu-id="48037-634">Int16</span></span>|  
|<span data-ttu-id="48037-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="48037-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="48037-636">String</span><span class="sxs-lookup"><span data-stu-id="48037-636">String</span></span>|  
|<span data-ttu-id="48037-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48037-637">DESCRIPTION</span></span>|<span data-ttu-id="48037-638">String</span><span class="sxs-lookup"><span data-stu-id="48037-638">String</span></span>|  
|<span data-ttu-id="48037-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="48037-639">DATE_CREATED</span></span>|<span data-ttu-id="48037-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-640">DateTime</span></span>|  
|<span data-ttu-id="48037-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="48037-641">DATE_MODIFIED</span></span>|<span data-ttu-id="48037-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="48037-643">Views</span><span class="sxs-lookup"><span data-stu-id="48037-643">Views</span></span>  
  
|<span data-ttu-id="48037-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-644">ColumnName</span></span>|<span data-ttu-id="48037-645">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-646">TABLE_CATALOG</span></span>|<span data-ttu-id="48037-647">String</span><span class="sxs-lookup"><span data-stu-id="48037-647">String</span></span>|  
|<span data-ttu-id="48037-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="48037-649">String</span><span class="sxs-lookup"><span data-stu-id="48037-649">String</span></span>|  
|<span data-ttu-id="48037-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-650">TABLE_NAME</span></span>|<span data-ttu-id="48037-651">String</span><span class="sxs-lookup"><span data-stu-id="48037-651">String</span></span>|  
|<span data-ttu-id="48037-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="48037-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="48037-653">String</span><span class="sxs-lookup"><span data-stu-id="48037-653">String</span></span>|  
|<span data-ttu-id="48037-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="48037-654">CHECK_OPTION</span></span>|<span data-ttu-id="48037-655">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-655">Boolean</span></span>|  
|<span data-ttu-id="48037-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="48037-656">IS_UPDATABLE</span></span>|<span data-ttu-id="48037-657">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-657">Boolean</span></span>|  
|<span data-ttu-id="48037-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48037-658">DESCRIPTION</span></span>|<span data-ttu-id="48037-659">String</span><span class="sxs-lookup"><span data-stu-id="48037-659">String</span></span>|  
|<span data-ttu-id="48037-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="48037-660">DATE_CREATED</span></span>|<span data-ttu-id="48037-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-661">DateTime</span></span>|  
|<span data-ttu-id="48037-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="48037-662">DATE_MODIFIED</span></span>|<span data-ttu-id="48037-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="48037-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="48037-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="48037-664">Indexes</span></span>  
  
|<span data-ttu-id="48037-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="48037-665">ColumnName</span></span>|<span data-ttu-id="48037-666">DataType</span><span class="sxs-lookup"><span data-stu-id="48037-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="48037-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-667">TABLE_CATALOG</span></span>|<span data-ttu-id="48037-668">String</span><span class="sxs-lookup"><span data-stu-id="48037-668">String</span></span>|  
|<span data-ttu-id="48037-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="48037-670">String</span><span class="sxs-lookup"><span data-stu-id="48037-670">String</span></span>|  
|<span data-ttu-id="48037-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-671">TABLE_NAME</span></span>|<span data-ttu-id="48037-672">String</span><span class="sxs-lookup"><span data-stu-id="48037-672">String</span></span>|  
|<span data-ttu-id="48037-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="48037-673">INDEX_CATALOG</span></span>|<span data-ttu-id="48037-674">String</span><span class="sxs-lookup"><span data-stu-id="48037-674">String</span></span>|  
|<span data-ttu-id="48037-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="48037-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="48037-676">String</span><span class="sxs-lookup"><span data-stu-id="48037-676">String</span></span>|  
|<span data-ttu-id="48037-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-677">INDEX_NAME</span></span>|<span data-ttu-id="48037-678">String</span><span class="sxs-lookup"><span data-stu-id="48037-678">String</span></span>|  
|<span data-ttu-id="48037-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="48037-679">PRIMARY_KEY</span></span>|<span data-ttu-id="48037-680">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-680">Boolean</span></span>|  
|<span data-ttu-id="48037-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="48037-681">UNIQUE</span></span>|<span data-ttu-id="48037-682">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-682">Boolean</span></span>|  
|<span data-ttu-id="48037-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="48037-683">CLUSTERED</span></span>|<span data-ttu-id="48037-684">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-684">Boolean</span></span>|  
|<span data-ttu-id="48037-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="48037-685">TYPE</span></span>|<span data-ttu-id="48037-686">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-686">Int32</span></span>|  
|<span data-ttu-id="48037-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="48037-687">FILL_FACTOR</span></span>|<span data-ttu-id="48037-688">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-688">Int32</span></span>|  
|<span data-ttu-id="48037-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="48037-689">INITIAL_SIZE</span></span>|<span data-ttu-id="48037-690">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-690">Int32</span></span>|  
|<span data-ttu-id="48037-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="48037-691">NULLS</span></span>|<span data-ttu-id="48037-692">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-692">Int32</span></span>|  
|<span data-ttu-id="48037-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="48037-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="48037-694">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-694">Boolean</span></span>|  
|<span data-ttu-id="48037-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="48037-695">AUTO_UPDATE</span></span>|<span data-ttu-id="48037-696">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-696">Boolean</span></span>|  
|<span data-ttu-id="48037-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="48037-697">NULL_COLLATION</span></span>|<span data-ttu-id="48037-698">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-698">Int32</span></span>|  
|<span data-ttu-id="48037-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="48037-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="48037-700">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-700">Int64</span></span>|  
|<span data-ttu-id="48037-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="48037-701">COLUMN_NAME</span></span>|<span data-ttu-id="48037-702">String</span><span class="sxs-lookup"><span data-stu-id="48037-702">String</span></span>|  
|<span data-ttu-id="48037-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="48037-703">COLUMN_GUID</span></span>|<span data-ttu-id="48037-704">Guid</span><span class="sxs-lookup"><span data-stu-id="48037-704">Guid</span></span>|  
|<span data-ttu-id="48037-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="48037-705">COLUMN_PROPID</span></span>|<span data-ttu-id="48037-706">Int64</span><span class="sxs-lookup"><span data-stu-id="48037-706">Int64</span></span>|  
|<span data-ttu-id="48037-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="48037-707">COLLATION</span></span>|<span data-ttu-id="48037-708">Int16</span><span class="sxs-lookup"><span data-stu-id="48037-708">Int16</span></span>|  
|<span data-ttu-id="48037-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="48037-709">CARDINALITY</span></span>|<span data-ttu-id="48037-710">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="48037-710">Decimal</span></span>|  
|<span data-ttu-id="48037-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="48037-711">PAGES</span></span>|<span data-ttu-id="48037-712">Int32</span><span class="sxs-lookup"><span data-stu-id="48037-712">Int32</span></span>|  
|<span data-ttu-id="48037-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="48037-713">FILTER_CONDITION</span></span>|<span data-ttu-id="48037-714">String</span><span class="sxs-lookup"><span data-stu-id="48037-714">String</span></span>|  
|<span data-ttu-id="48037-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="48037-715">INTEGRATED</span></span>|<span data-ttu-id="48037-716">ブール型</span><span class="sxs-lookup"><span data-stu-id="48037-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48037-717">関連項目</span><span class="sxs-lookup"><span data-stu-id="48037-717">See also</span></span>

- [<span data-ttu-id="48037-718">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="48037-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

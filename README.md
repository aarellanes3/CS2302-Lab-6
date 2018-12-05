# CS2302-Lab-6
from queue import Queue
import DSF

def sort_edges(graph):
    return graph

def krs_algorithm(graph):
    mst = []
    sorted_edges = sort_edges(graph.get_edges())
    dsf = DSF(graph.get_numvertices())
    for edge in sorted_edges:
        if dsf.find(edge.src) != dsf.find(edge.dest):
            mst.append(edge)
            dsf.union(edge.src, edge.dest)
    return mst

def compute_in_degree(graph):
    n = graph.get_numvertices()
    for i in n:
        count = graph.get_vertices_rachapble_from(n[i])
    return count

def topological_sort(graph):
    all_in_degrees = compute_in_degree(graph)
    sort_result = []

    q = Queue()

    for i in range(len(all_in_degrees)):
        if all_in_degrees[i] == 0
            q.put(i)

    while not  q.isempty():
        u = q.put()

        sort_result.append(u)

        for adj_vertex in graph.get_vertices_reachable_from(u):
            all_in_degrees[adj_vertex] -=1

            if all_in_degrees[adj_vertex] == 0:

        if len(sort_result) != graph.numvertices():
            return None

        return sort_result
